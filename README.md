# Palak-GDSC-AppDev_Task1
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

class RForm extends Canvas implements ActionListener
{
JFrame jf;
JLabel name,password;
JCheckBox show;
JTextField tname,details;
JPasswordField tpass;
JButton ok,reset;
ImageIcon icon;

    

RForm()
{
jf = new JFrame("Login Form");
tname = new JTextField(10);
name = new JLabel("Username");
password = new JLabel("Password");
show = new JCheckBox("Show password");
tpass = new JPasswordField(10);
ok = new JButton("LOGIN");
reset = new JButton("RESET");
icon = new ImageIcon("icon.png");

jf.setLayout(new FlowLayout());

jf.add(new JLabel(icon));
jf.pack();

jf.add(name);
jf.add(tname);
jf.add(password);
jf.add(tpass);
jf.add(ok);
jf.add(reset);
jf.add(show);


ok.addActionListener(this);
reset.addActionListener(this);

jf.setSize(500,100);
jf.setVisible(true);
}

public void actionPerformed(ActionEvent e)
{
if(show.isSelected())
{
	tpass.setEchoChar((char)0);
}
else
{
	tpass.setEchoChar('*');
}
if(e.getSource()==ok)
{
String s1 = tname.getText();
String s2 = String.valueOf(tpass.getPassword());
}

else if(e.getSource()==reset)
{
tname.setText("");
tpass.setText("");
}
}

public static void main(String args[])
{
RForm r = new RForm();
}
}
