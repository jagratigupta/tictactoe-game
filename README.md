package myfirstprog;

import javax.swing.JFrame;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import javax.swing.JButton;
import java.awt.Color;
import java.awt.Font;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.JFormattedTextField;
import javax.swing.JTextField;

public class TicTacTo extends JFrame {

	/**
	 * Launch the application.
	 */
	private boolean isXorZero=true;
	JButton b1=new JButton("");
	JButton b2=new JButton("");
	JButton b3=new JButton("");
	JButton b4=new JButton("");
	JButton b5=new JButton("");
	JButton b6=new JButton("");
	JButton b7=new JButton("");
	JButton b8=new JButton("");
	JButton b9=new JButton("");
   private JPanel contentPane;
 
	private boolean isButBlank(JButton button){
		if(button.getText().trim().length()==0)
			return true;
		else
			return false;
	}
	private boolean isRowBlank(JButton bt1,JButton bt2,JButton bt3){
		if(isButBlank(bt1)&&isButBlank(bt2)&&isButBlank(bt3))
			return true;
		else
			return false;
	}
	private boolean isRowMatch(JButton bt1,JButton bt2,JButton bt3){
		if(!isRowBlank(bt1,bt2,bt3)){
			if(bt1.getText().equals(bt2.getText())&&bt1.getText().equals(bt3.getText()))
				return true;
			else
				return false;
		}
		else
			return false;
	}
	private boolean isGameOver()
	{
		if(isRowMatch(b1,b2,b3)){
			return true;
		}
		else 
			if(isRowMatch(b1,b4,b7)){
			return true;
			}
		else 
			if(isRowMatch(b1,b5,b9)){
			return true;
			}
		else 
			if(isRowMatch(b2,b5,b8)){
				return true;
				}
		else 
			if(isRowMatch(b3,b6,b9)){
			   return true;
				}
		else 
			if(isRowMatch(b4,b5,b6)){
			   return true;
				}
		else 
			if(isRowMatch(b3,b5,b7)){
				return true;
				}
		else 
			if(isRowMatch(b7,b8,b9)){
				return true;
				}
		return false;
	}
	
	private void resetGame(){
		b1.setText("");
		b2.setText("");
		b3.setText("");
		b4.setText("");
		b5.setText("");
		b6.setText("");
		b7.setText("");
		b8.setText("");
		b9.setText("");
		
	}
	
	private void PrintText(JButton button){
		if(isButBlank(button)){
			if(isXorZero)
				button.setText("X");
			else
				button.setText("O");
			isXorZero=!isXorZero;
			if(isGameOver()){
				JOptionPane.showMessageDialog(this
						, "Game Over "+button.getText()+" U Win");
				isXorZero=true;
				resetGame();
			}
				
			else
					if(b1.getText().length() >= 1 && b2.getText().length() >= 1&& b3.getText().length() >= 1&&b4.getText().length() >= 1&&b5.getText().length() >= 1&&b6.getText().length() >= 1
							&&b7.getText().length() >= 1&&b8.getText().length() >= 1&&b9.getText().length() >= 1){
					
						JOptionPane.showMessageDialog(this,"Game Draw")	;
						resetGame();
					}
				
			}

		}
	public static void main(String[] args) {
		TicTacTo frame = new TicTacTo();
		frame.setVisible(true);
		
		}

	/**
	 * Create the frame.
	 */
	public TicTacTo() {
		
		setTitle("TicTacToe-Game2016");
		setResizable(false);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 450, 300);
		contentPane = new JPanel();
		contentPane.setBackground(new Color(0, 0, 102));
		contentPane.setLayout(null);
		setContentPane(contentPane);
		

		b1.setBackground(new Color(204, 255, 153));
		b1.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				PrintText(b1);
			}
		});
		b1.setFont(new Font("Simplified Arabic Fixed", Font.BOLD, 20));
		b1.setBounds(31, 36, 89, 41);
		contentPane.add(b1);
		b2.setFont(new Font("Simplified Arabic Fixed", Font.BOLD, 20));
		
		
		b2.setBackground(new Color(255, 192, 203));
		b2.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				PrintText(b2);
			}
		});
		b2.setBounds(166, 36, 89, 41);
		contentPane.add(b2);
		b3.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				PrintText(b3);
			}
		});
		
		
		b3.setBackground(new Color(204, 255, 153));
		b3.setBounds(309, 36, 89, 41);
		contentPane.add(b3);
		b3.setFont(new Font("Simplified Arabic Fixed", Font.BOLD, 20));
		b4.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				PrintText(b4);
			}
		});
		
		
		b4.setBackground(new Color(255, 192, 203));
		b4.setBounds(31, 121, 89, 41);
		contentPane.add(b4);
		b4.setFont(new Font("Simplified Arabic Fixed", Font.BOLD, 20));
		b5.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				PrintText(b5);
			}
		});
		
		
		b5.setBackground(new Color(204, 255, 153));
		b5.setBounds(166, 121, 89, 41);
		contentPane.add(b5);
		b5.setFont(new Font("Simplified Arabic Fixed", Font.BOLD, 20));
		b6.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				PrintText(b6);
			}
		});
		
		
		b6.setBackground(new Color(255, 192, 203));
		b6.setBounds(309, 122, 89, 41);
		contentPane.add(b6);
		b6.setFont(new Font("Simplified Arabic Fixed", Font.BOLD, 20));
		b7.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				PrintText(b7);
			}
		});
		
		
		b7.setBackground(new Color(204, 255, 153));
		b7.setBounds(31, 213, 89, 41);
		contentPane.add(b7);
		b7.setFont(new Font("Simplified Arabic Fixed", Font.BOLD, 20));
		b8.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				PrintText(b8);
			}
		});
		
		
		b8.setBackground(new Color(255, 192, 203));
		b8.setBounds(166, 213, 89, 41);
		contentPane.add(b8);
		b8.setFont(new Font("Simplified Arabic Fixed", Font.BOLD, 20));
		b9.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				PrintText(b9);
			}
		});
		
		
		b9.setBackground(new Color(204, 255, 153));
		b9.setBounds(309, 213, 89, 41);
		contentPane.add(b9);
		b9.setFont(new Font("Simplified Arabic Fixed", Font.BOLD, 20));
		
	}
}

