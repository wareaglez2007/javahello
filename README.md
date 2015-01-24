/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */

package hellojava2;
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
/**
 *
 * @author rostomsahakian
 */


public class HelloJava2
{
  public static void main( String[] args ) {
    JFrame frame = new JFrame( "HelloJava2" );
    frame.add( new HelloComponent2("Drag me!") );
	frame.setDefaultCloseOperation( JFrame.EXIT_ON_CLOSE );
    frame.setSize( 300, 300 );
    frame.setVisible( true );
  }
}

class HelloComponent2 extends JComponent 
	implements MouseMotionListener 
{
  String theMessage;
  int mouseX= 125, mouseY= 95; // Coordinates of the mouse

  public HelloComponent2( String message ) {
    theMessage = message;
    addMouseMotionListener(this);
  }

  public void paintComponent( Graphics g ) {
    g.drawString(theMessage, mouseX, mouseY);
  }

  public void mouseDragged(MouseEvent e) {
    // Save the mouse coordinates and paint the message.
    mouseX = e.getX();
    mouseY = e.getY();
    repaint();
  }

  public void mouseMoved(MouseEvent e) { }
}
