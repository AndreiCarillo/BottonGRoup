# BottonGRoup
Tarea Unidad 1 Topicos Avanzados de programación
package Lasweas;
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class AgruparBotones extends JFrame implements ActionListener {
	JPanel panelA;
	JButton botonA,botonB;

    public AgruparBotones(String titulo) {
        //Creacio?n de los RadioButtons
    	this.setBounds(4,90,80,30);
    	this.setVisible(true);
    	panelA = new JPanel();
    	setContentPane(panelA);
    	panelA.setLayout(new FlowLayout());
    	botonA = new JButton ("Boton A");
    	botonB = new JButton("Boton B");
        JRadioButton LoroButton = new JRadioButton("Loro");
        LoroButton.setMnemonic(KeyEvent.VK_B);
        LoroButton.setActionCommand("Loro");
        LoroButton.setSelected(true);

        JRadioButton GuacaButton = new JRadioButton("Guacamayo");
        GuacaButton.setMnemonic(KeyEvent.VK_C);
        GuacaButton.setActionCommand("Guacamayo");

        JRadioButton BuitButton = new JRadioButton("Buitre");
        BuitButton.setMnemonic(KeyEvent.VK_D);
        BuitButton.setActionCommand("Buitre");

        JRadioButton AguiButton = new JRadioButton("Aguila");
        AguiButton.setMnemonic(KeyEvent.VK_R);
        AguiButton.setActionCommand("Aguila");

        JRadioButton DodoButton = new JRadioButton("Dodo");
        DodoButton.setMnemonic(KeyEvent.VK_P);
        DodoButton.setActionCommand("Dodo");

        ButtonGroup btgAnimalitos = new ButtonGroup();

        btgAnimalitos.add(LoroButton);
        btgAnimalitos.add(GuacaButton);
        btgAnimalitos.add(BuitButton);
        btgAnimalitos.add(AguiButton);
        btgAnimalitos.add(DodoButton);

        JPanel radioPanel = new JPanel();
        radioPanel.setLayout(new GridLayout(0,1));
        //radioPanel.setLayout(new BoxLayout(radioPanel, BoxLayout.Y_AXIS));
        radioPanel.add(LoroButton);
        radioPanel.add(GuacaButton);
        radioPanel.add(BuitButton);
        radioPanel.add(AguiButton);
        radioPanel.add(DodoButton);
        radioPanel.setBackground(Color.GREEN);

        JLabel picture = new JLabel(new ImageIcon("src/Lasweas/loro.png"));

        /*BoxLayout distBoxLayout = new BoxLayout(this.getContentPane(),
                                                BoxLayout.X_AXIS);
        getContentPane().setLayout(distBoxLayout);
        */

        GridLayout distGrid = new GridLayout(2,2);
        getContentPane().setLayout(distGrid);
        getContentPane().add(radioPanel);
        getContentPane().add(picture);
        getContentPane().add(botonA);
        getContentPane().add(botonB);

        /*
        getContentPane().add(radioPanel, BorderLayout.WEST);
        getContentPane().add(picture,BorderLayout.CENTER);
        */

        getContentPane().setBackground(Color.BLUE);

        pack();

        setTitle(titulo);
    }

    public void actionPerformed(ActionEvent e) {
        System.out.println("Evento producido por " + e.getActionCommand());
    }

    public static void main (String[] args) {
        WindowListener l = new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        };

        JFrame frame = new AgruparBotones("Curso de Java: Agrupar Botones");
        frame.addWindowListener(l);

        frame.pack();
        frame.setVisible(true);
    }
}
