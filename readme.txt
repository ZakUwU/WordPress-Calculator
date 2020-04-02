Calculatrice scientifique-------------------------
=========

Ce document intitulé « Calculatrice scientifique » est mis à disposition sous les termes de
la licence Creative Commons. Vous pouvez copier, modifier des copies de cette
source, dans les conditions fixées par la licence, tant que cette note
apparaît clairement.

Description :
=============

ce code sert &agrave; creer une calculatrice scientifiqueavec une belle et simpl
e interface .
<br />vous pouvez basculer entre le mode standard et le mode scie
ntifique en cliquant sur un simple bouton radio.
<br />cette calculatrice compr
is les differentes convertions entre les bases decimale,binaire,octale et hexade
cimale.
<br />elle prend en charge la gestion des erreur de saisie.
<br /><a n
ame='source-exemple'></a><h2> Source / Exemple : </h2>
<br /><pre class='code'
 data-mode='basic'>
import javax.swing.*;
import java.awt.*;
import java.awt.
event.*;
class Calculatrice extends JFrame implements ActionListener,ItemListen
er
{   //JFrame frame=new JFrame();On peut ne pas l'inserer si on fait extends 
JFrame
	JButton b0,b1,b2,b3,b4,b5,b6,b7,b8,b9,b,bexp,bc,bcl,bMult,bDiv,bSom,bSo
ust;
	JButton bRes,bOff,bX1Y,b1X,bpm,bSqrt,bLog,bRand,bnCr,bnAr,bFact,bSin,bCos
;
	JButton bTan,bPuis,bX2,b10x,bEx,bF,bE,bD,bC,bB,bA,b2ndF;
	JRadioButton Scie
,Norm,Bin,Dec,Oct,Hex;
	ButtonGroup bg1,bg2;
	JPanel pTxt,p2,p3;
	JTextField 
txt;
	double xp=1,xs=0,aux=0;
	boolean op=false,mult=false,div=false,som=false
,soust=false,init=true;
	boolean dec=true,bin=false,oct=false,hex=false,YX=fals
e,X1Y=false;
	boolean nAr=false,nCr=false,shift=false,virg=false;
	Calculatric
e()
	{
	super(&quot;Calculatrice Made By AMF&quot;);
	// Initialisation des b
outon et champs de saisie
	b0=new JButton(&quot;0&quot;);b1=new JButton(&quot;1
&quot;);b2=new JButton(&quot;2&quot;);
	b3=new JButton(&quot;3&quot;);b4=new JB
utton(&quot;4&quot;);b5=new JButton(&quot;5&quot;);
	b6=new JButton(&quot;6&quo
t;);b7=new JButton(&quot;7&quot;);b8=new JButton(&quot;8&quot;);
	b9=new JButto
n(&quot;9&quot;);b=new JButton(&quot;.&quot;);bexp=new JButton(&quot;Pi&quot;);

	bX1Y=new JButton(&quot;X^(1/Y)&quot;);bpm=new JButton(&quot;+/-&quot;);bMult=n
ew JButton(&quot;*&quot;);
	bDiv=new JButton(&quot;/&quot;);bSom=new JButton(&q
uot;+&quot;);bSoust=new JButton(&quot;-&quot;);
	bRes=new JButton(&quot;=&quot;
);b1X=new JButton(&quot;1/X&quot;);txt =new JTextField(&quot;0&quot;);
	bSqrt=n
ew JButton(&quot;Rac&quot;);bLog=new JButton(&quot;Ln/Log&quot;);bRand=new JButt
on(&quot;Rand&quot;);
	bnCr=new JButton(&quot;nCr&quot;);bnAr=new JButton(&quot
;nAr&quot;);bFact=new JButton(&quot;n!&quot;);
	bSin=new JButton(&quot;Sin&quot
;);bCos=new JButton(&quot;Cos&quot;);bTan=new JButton(&quot;Tan&quot;);
	bPuis=
new JButton(&quot;Y^X&quot;);bX2=new JButton(&quot;X^2&quot;);b10x=new JButton(&
quot;10^x&quot;);
	bEx=new JButton(&quot;e^x&quot;);bF=new JButton(&quot;F&quot
;);bE=new JButton(&quot;E&quot;);
	bD=new JButton(&quot;D&quot;);bC=new JButton
(&quot;C&quot;);bB=new JButton(&quot;B&quot;);
	bA=new JButton(&quot;A&quot;);b
2ndF=new JButton(&quot;2nF&quot;);bc=new JButton(&quot;C&quot;);
	bOff=new JBut
ton(&quot;OFF&quot;);bcl=new JButton(&quot;Del&quot;);
	Scie=new JRadioButton(&
quot;Sci&quot;);Norm=new JRadioButton(&quot;Std&quot;);
	Bin=new JRadioButton(&
quot;Bin&quot;);Dec=new JRadioButton(&quot;Dec&quot;);
	Oct=new JRadioButton(&q
uot;Oct&quot;);Hex=new JRadioButton(&quot;Hex&quot;);
	bg1=new ButtonGroup();bg
2=new ButtonGroup();
	bg1.add(Norm);bg1.add(Scie);bg2.add(Bin);bg2.add(Oct);bg2
.add(Hex);bg2.add(Dec);
	Dec.setSelected(true);Norm.setSelected(true);
	bA.set
Enabled(false);bB.setEnabled(false);bC.setEnabled(false);
	bD.setEnabled(false)
;bE.setEnabled(false);bF.setEnabled(false);
	// Definir la taille préférer des 
composants
	b0.setPreferredSize(new Dimension(80,30));b1.setPreferredSize(new D
imension(80,30));
	b2.setPreferredSize(new Dimension(80,30));b3.setPreferredSiz
e(new Dimension(80,30));
	b4.setPreferredSize(new Dimension(80,30));b5.setPrefe
rredSize(new Dimension(80,30));
	b6.setPreferredSize(new Dimension(80,30));b7.s
etPreferredSize(new Dimension(80,30));
	b8.setPreferredSize(new Dimension(80,30
));b9.setPreferredSize(new Dimension(80,30));
	b.setPreferredSize(new Dimension
(80,30));bexp.setPreferredSize(new Dimension(80,30));
	bDiv.setPreferredSize(ne
w Dimension(80,30));bSom.setPreferredSize(new Dimension(80,30));
        bSoust
.setPreferredSize(new Dimension(80,30));bRes.setPreferredSize(new Dimension(165,
30));
	bX1Y.setPreferredSize(new Dimension(80,30));b1X.setPreferredSize(new Dim
ension(80,30));
	bpm.setPreferredSize(new Dimension(80,30));bMult.setPreferredS
ize(new Dimension(80,30));
	bSqrt.setPreferredSize(new Dimension(80,30));bLog.s
etPreferredSize(new Dimension(80,30));
	bRand.setPreferredSize(new Dimension(80
,30));bnCr.setPreferredSize(new Dimension(80,30));
	bnAr.setPreferredSize(new D
imension(80,30));bFact.setPreferredSize(new Dimension(80,30));
	bCos.setPreferr
edSize(new Dimension(80,30));bPuis.setPreferredSize(new Dimension(80,30));
	bX2
.setPreferredSize(new Dimension(80,30));b10x.setPreferredSize(new Dimension(80,3
0));
	bEx.setPreferredSize(new Dimension(80,30));bF.setPreferredSize(new Dimens
ion(80,30));
	bE.setPreferredSize(new Dimension(80,30));bD.setPreferredSize(new
 Dimension(80,30));
	bC.setPreferredSize(new Dimension(80,30));bB.setPreferredS
ize(new Dimension(80,30));
	bA.setPreferredSize(new Dimension(80,30));b2ndF.set
PreferredSize(new Dimension(80,30));
	Scie.setPreferredSize(new Dimension(80,30
));Norm.setPreferredSize(new Dimension(80,30));
	Bin.setPreferredSize(new Dimen
sion(80,30));Dec.setPreferredSize(new Dimension(80,30));
	Oct.setPreferredSize(
new Dimension(80,30));Hex.setPreferredSize(new Dimension(80,30));
	bSin.setPref
erredSize(new Dimension(80,30));bc.setPreferredSize(new Dimension(80,30));
	bOf
f.setPreferredSize(new Dimension(80,30));bcl.setPreferredSize(new Dimension(80,3
0));
	bTan.setPreferredSize(new Dimension(80,30));txt.setPreferredSize(new Dime
nsion(440,35));
	txt.setHorizontalAlignment(SwingConstants.RIGHT);
	txt.setBac
kground(Color.black);txt.setForeground(Color.GREEN);
	txt.setFont(new Font(&quo
t;DIALOG&quot;,Font.CENTER_BASELINE+Font.BOLD,12));
	// Declaration des Panel e
t leurs contenues
	JPanel pNorm=new JPanel();
	pNorm.add(b7);pNorm.add(b8);pNo
rm.add(b9);pNorm.add(bexp);pNorm.add(bSqrt);
	pNorm.add(b4);pNorm.add(b5);pNorm
.add(b6);pNorm.add(bMult);pNorm.add(bDiv);
	pNorm.add(b1);pNorm.add(b2);pNorm.a
dd(b3);pNorm.add(bSom);pNorm.add(bSoust);
	pNorm.add(b0);pNorm.add(b);pNorm.add
(bpm);pNorm.add(bRes);
	p2=new JPanel(new GridLayout(1,1));p2.add(pNorm);
	JPa
nel pStd=new JPanel();pStd.add(Scie);pStd.add(Norm);pStd.add(bcl);
	pStd.add(bc
);pStd.add(bOff);
	JPanel pSci=new JPanel();
	pSci.add(Bin);pSci.add(Oct);pSci
.add(Hex);pSci.add(Dec);pSci.add(b2ndF);
	pSci.add(bA);pSci.add(bB);pSci.add(bC
);pSci.add(bD);pSci.add(bE);
	pSci.add(bPuis);pSci.add(bX2);pSci.add(b10x);pSci
.add(bEx);pSci.add(bF);
	pSci.add(bFact);pSci.add(bLog);pSci.add(bSin);pSci.add
(bCos);pSci.add(bTan);
	pSci.add(bX1Y);pSci.add(b1X);pSci.add(bRand);pSci.add(b
nCr);pSci.add(bnAr);
	p3 =new JPanel(new GridLayout(1,1)); p3.add(pSci);
	pTxt
=new JPanel();pTxt.add(txt);pTxt.add(pStd);
	// Ajout des écouteurs aux deffire
nts boutons
        b0.addActionListener(this);b1.addActionListener(this);b2.ad
dActionListener(this);
        b3.addActionListener(this);b4.addActionListener(
this);b5.addActionListener(this);
        b6.addActionListener(this);b7.addActi
onListener(this);b8.addActionListener(this);
        b9.addActionListener(this)
;b.addActionListener(this);bexp.addActionListener(this);
        b1X.addActionL
istener(this);bpm.addActionListener(this);bMult.addActionListener(this);
      
  bDiv.addActionListener(this);bSom.addActionListener(this);bSoust.addActionList
ener(this);
        bRes.addActionListener(this);bX1Y.addActionListener(this);b
c.addActionListener(this);
        bcl.addActionListener(this);bOff.addActionLi
stener(this);bSqrt.addActionListener(this);
        bLog.addActionListener(this
);bRand.addActionListener(this);bnCr.addActionListener(this);
        bnAr.addA
ctionListener(this);bFact.addActionListener(this);bSin.addActionListener(this);

        bCos.addActionListener(this);bTan.addActionListener(this);bPuis.addActi
onListener(this);
        bX2.addActionListener(this);b10x.addActionListener(th
is);bEx.addActionListener(this);
        b2ndF.addActionListener(this);bA.addAc
tionListener(this);bB.addActionListener(this);
        bC.addActionListener(thi
s);bD.addActionListener(this);bE.addActionListener(this);
        bF.addActionL
istener(this);
        Scie.addItemListener(this);Norm.addItemListener(this);Bi
n.addItemListener(this);
        Dec.addItemListener(this);Oct.addItemListener(
this);Hex.addItemListener(this);
        // Mise en forme de la fenetre
      
  // ImageIcon image=new ImageIcon(&quot;Clock.png&quot;);
        // this.setI
conImage(image.getImage());
        this.setSize(new Dimension(452,331));
    
    this.getContentPane().setLayout(new GridLayout(2,1));
        this.getConte
ntPane().add(pTxt);this.getContentPane().add(p2);
        this.setLocation(300,
100);
        this.setCursor(12);this.setResizable(true);this.show();
        
this.setDefaultCloseOperation(EXIT_ON_CLOSE);
        }
    void activatehex(b
oolean b)
    {
    bA.setEnabled(b);bB.setEnabled(b);bC.setEnabled(b);
	bD.s
etEnabled(b);bE.setEnabled(b);bF.setEnabled(b);	
    }
    void activateP2P3(b
oolean v)
    {
    b0.setEnabled(v);b1.setEnabled(v);b2.setEnabled(v);b3.setE
nabled(v);
    b4.setEnabled(v);b5.setEnabled(v);b6.setEnabled(v);b7.setEnabled
(v);
    b8.setEnabled(v);b9.setEnabled(v);b.setEnabled(v);bexp.setEnabled(v);

    bMult.setEnabled(v);bDiv.setEnabled(v);bSom.setEnabled(v);bSoust.setEnabled
(v);
    bRes.setEnabled(v);bX1Y.setEnabled(v);b1X.setEnabled(v);bpm.setEnabled
(v);
    bSqrt.setEnabled(v);bLog.setEnabled(v);bRand.setEnabled(v);bnCr.setEna
bled(v);
    bnAr.setEnabled(v);bFact.setEnabled(v);bSin.setEnabled(v);bCos.set
Enabled(v);
	bTan.setEnabled(v);bPuis.setEnabled(v);bX2.setEnabled(v);b10x.setE
nabled(v);
	bEx.setEnabled(v);b2ndF.setEnabled(v);Scie.setEnabled(v);
	Norm.se
tEnabled(v);Bin.setEnabled(v);Dec.setEnabled(v);Oct.setEnabled(v);
	Hex.setEnab
led(v);bA.setEnabled(v);bB.setEnabled(v);bC.setEnabled(v);
	bD.setEnabled(v);bE
.setEnabled(v);bF.setEnabled(v);
    }
    void activateOp(boolean v)
    {

    b.setEnabled(v);bexp.setEnabled(v);bMult.setEnabled(v);bDiv.setEnabled(v);

    bSom.setEnabled(v);bSoust.setEnabled(v);bRes.setEnabled(v);bX1Y.setEnabled(v
);
    b1X.setEnabled(v);bpm.setEnabled(v);bSqrt.setEnabled(v);bLog.setEnabled(
v);
    bRand.setEnabled(v);bnCr.setEnabled(v);bnAr.setEnabled(v);bFact.setEnab
led(v);
    bSin.setEnabled(v);bCos.setEnabled(v);bTan.setEnabled(v);bPuis.setE
nabled(v);
    bX2.setEnabled(v);b10x.setEnabled(v);bEx.setEnabled(v);b2ndF.set
Enabled(v);
    }
    int detBaseSource()
    {
    	if(dec) return 10;
   
 	else if(bin) return 2;
    	else if(oct) return 8;
    	else  return 16;
  
  }
    int detBaseDestination(Object src)
    {
    	if(src==Dec)
    	{
 
   		dec=true;bin=false;oct=false;hex=false;
    		activatehex(false);activateO
p(true);
    		b0.setEnabled(true);b1.setEnabled(true);b2.setEnabled(true);
  
  		b3.setEnabled(true);b4.setEnabled(true);b5.setEnabled(true);
    		b6.setEn
abled(true);b7.setEnabled(true);b8.setEnabled(true);
    		b9.setEnabled(true);

    		return 10;
    	}
    	else if(src==Bin)
    	{
    		dec=false;bin=
true;oct=false;hex=false;
    		activatehex(false);activateOp(false);
    		b0
.setEnabled(true);b1.setEnabled(true);b2.setEnabled(false);
    		b3.setEnabled
(false);b4.setEnabled(false);b5.setEnabled(false);
    		b6.setEnabled(false);b
7.setEnabled(false);b8.setEnabled(false);
    		b9.setEnabled(false);
    		re
turn 2;
    	}
    	else if(src==Oct)
    	{
    		dec=false;bin=false;oct=t
rue;hex=false;
    		activatehex(false);activateOp(false);
    		b0.setEnabled
(true);b1.setEnabled(true);b2.setEnabled(true);
    		b3.setEnabled(true);b4.se
tEnabled(true);b5.setEnabled(true);
    		b6.setEnabled(true);b7.setEnabled(tru
e);b8.setEnabled(false);
    		b9.setEnabled(false);    		
    		return 8;
  
  	}
    	else
    	{
    		dec=false;bin=false;oct=false;hex=true;
    		ac
tivatehex(true);activateOp(false);
    		b0.setEnabled(true);b1.setEnabled(true
);b2.setEnabled(true);
    		b3.setEnabled(true);b4.setEnabled(true);b5.setEnab
led(true);
    		b6.setEnabled(true);b7.setEnabled(true);b8.setEnabled(true);

    		b9.setEnabled(true); 
    		return 16;
    	}
    }
    int conversion
Carct(char c)
    {
    	if(c=='F') return 15;
    	else if(c=='E') return 14
;
    	else if(c=='D') return 13;
    	else if(c=='C') return 12;
    	else i
f(c=='B') return 11;
    	else if(c=='A') return 10;
    	else return(Characte
r.getNumericValue(c));
    }
    char toHexaCarct(int x)
    {
    	if(x==10
) return 'A';
    	else if(x==11) return 'B';
    	else if(x==12) return 'C';

    	else if(x==13) return 'D';
    	else if(x==14) return 'E';
    	else ret
urn 'F';
    }
    boolean isValide(String s)
    {
    	for(int i=0;i&lt;s.
length();i++)
    	{
    		if(s.charAt(i)=='.' || s.charAt(i)=='-')
    		ret
urn false;
    	}
    	return true;
    }
    int toDec(String dep,int bs)

    {
    int i=(dep.length())-1;
    String s=dep;
    int puis=0;
    int 
res=0;
    while(i&gt;=0)
    {
    	res=res+conversionCarct(s.charAt(i))*((i
nt)(Math.pow(bs,puis)));
    	puis++;
    	i--;
    }
    return res;
    }

    String fromDec(String dep,int bd)
    {
       	String s=&quot;&quot;;

    	int aux=Integer.parseInt(dep);
    	while(aux/bd!=0)
    	{
    		if(aux
%bd&lt;10)
    		{s=(aux%bd)+s;}
    		else
    		{s=toHexaCarct(aux%bd)+s;}

    		aux=aux/bd;
    	}
    	if(aux%bd&lt;10) {s=(aux%bd)+s;}
    	else {s=
toHexaCarct(aux%bd)+s;}
    	return s;
    }
    void Resultat()
    {
    
	double x2=Double.parseDouble(txt.getText());
    	if(mult) {txt.setText(&quot;
&quot;+(xp*x2));xp=Double.parseDouble(txt.getText());}
		else if(div) 
		{
		
	if(x2!=0)
			{
			txt.setText(&quot;&quot;+(xp/x2));
			xp=Double.parseDoubl
e(txt.getText());
			}
			else
			{
				activateP2P3(false);
				txt.setBac
kground(Color.LIGHT_GRAY);txt.setForeground(Color.RED);
				txt.setText(&quot; 
 ERROR !!  DIVISION   PAR   ZERO   IMPOSSIBLE  &quot;);
			}		
		}
		else if(
som) {txt.setText(&quot;&quot;+(xs+x2));xs=Double.parseDouble(txt.getText());}

		else if(soust){ txt.setText(&quot;&quot;+(xs-x2));xs=Double.parseDouble(txt.ge
tText());}
		else if(YX)	{double res=Math.pow(aux,x2);txt.setText(&quot;&quot;+
res);}
		else if(nAr)
		{
			if((aux&gt;=x2)&amp;&amp;(aux&gt;=0)&amp;&amp;(x
2&gt;=0))
			{
			double res=(fact(aux)/fact((aux-x2)));
			txt.setText(&quot
;&quot;+res);
			}
			else
			{
				txt.setBackground(Color.LIGHT_GRAY);txt.
setForeground(Color.RED);
				txt.setText(&quot;  ERROR!!  RULE  :  \&quot;  n 
 doit  etre &gt;= r  et  n &gt;= 0  et  r &gt;= 0  \&quot; &quot;);
			    acti
vateP2P3(false);}
		}
		else if(nCr)
		{
			if((aux&gt;=x2)&amp;&amp;(aux&gt
;=0)&amp;&amp;(x2&gt;=0))
			{
				double res=(fact(aux)/(fact(x2)*fact((aux-x
2))));
				txt.setText(&quot;&quot;+res);
			}
			else
			{
				txt.setBack
ground(Color.LIGHT_GRAY);txt.setForeground(Color.RED);
				txt.setText(&quot; E
RROR!!   RULE  :  \&quot;  n  doit  etre  &gt;= r  et  n  &gt;= 0  et  r  &gt;= 
0  \&quot; &quot;);
			    activateP2P3(false);}
		}
		else if(X1Y)
		{
			
if(x2!=0)
			{double res=Math.pow(aux,(1/x2));txt.setText(&quot;&quot;+res);}

			else
			{
				txt.setBackground(Color.LIGHT_GRAY);txt.setForeground(Color.R
ED);
				txt.setText(&quot; ERROR!!  DEUXIEME  NOMBRE  DOIT  ETRE  DIFFERENT  D
E  0 &quot;);
			    activateP2P3(false);}
		}
		 init=false;   
		 virg=fal
se; 
    }
    double fact(double x)
    {
    	double res=1;
    	if(x&gt;
=0)
    	{
    	for(int i=2;i&lt;=x;i++)
		{
			res=res*i;
		}
		return re
s;
		}
		else return 0;
    }
	public void actionPerformed(ActionEvent e)
	
{
		Object src = e.getSource();
		JButton baux=(JButton)src;
		////////////**
*******Bouton des chiffres********//////////////
		if((src==b0)||src==b1||src==
b2||src==b3||src==b4||src==b5||src==b6||src==b7||src==b8||src==b9||src==bA||src=
=bB||src==bC||src==bD||src==bE||src==bF)
		{ 
		if(!op) txt.setText(txt.getTex
t()+baux.getLabel());
		else if(op)
		{
			txt.setText(baux.getLabel());
			
op=false;
		}
		}
		////////////*********Bouton virgule********//////////////

		else if(src==b)
		{
			if(!virg)
			{
				txt.setText(txt.getText()+&quo
t;.&quot;);
				virg=true;
			}
		}
		////////////*********Bouton Pi********
//////////////
		else if(src==bexp)
		{
			txt.setText(&quot;&quot;+Math.PI);

			virg=true;
		}
		////////////*********Bouton clear********//////////////

		else if(src==bc)
		{txt.setText(&quot;0&quot;);xp=1;xs=0;init=true;aux=0;shi
ft=false;op=false;X1Y=true;
		mult=false;div=false;som=false;soust=false;nAr=fa
lse;nCr=false;
		activateP2P3(true);activatehex(false);Dec.setSelected(true);vi
rg=false;
		txt.setBackground(Color.black);txt.setForeground(Color.GREEN);}
		
////////////*********Bouton de +/-********//////////////
		else if(src==bpm)
	
	txt.setText(&quot;&quot;+Double.parseDouble(txt.getText())*-1);
		else if(src=
=bcl)
		 txt.setText(txt.getText().substring(0,txt.getText().length()-1));
		 

		 ////////////*********Multiplication********//////////////
		else if(src==b
Mult)
		{
		try
		{
		if(init || op)
		{
			xp=(Double.parseDouble(txt.get
Text()));
			init=false;virg=false;
			txt.setText(&quot;&quot;+xp);
		}
		e
lse
		{
			Resultat();
			xp=(Double.parseDouble(txt.getText()));
		}
			op
=true;mult=true;div=false;som=false;soust=false;YX=false;
			nAr=false;nCr=fals
e;X1Y=true;
		}catch(NumberFormatException execp)
    	{
    		txt.setBackgro
und(Color.LIGHT_GRAY);txt.setForeground(Color.RED);
    		txt.setText(&quot;ERR
OR :  CONVERTION  AVEC  VERGULE  FLOTTANTE  NON  SUPPORTEE &quot;);
	     	acti
vateP2P3(false);}
		}
		////////////*******Division******////////////
		else 
if(src==bDiv)
		{
		try
		{
		if(init || op)
		{
			xp=(Double.parseDouble
(txt.getText()));
			init=false;virg=false;
			txt.setText(&quot;&quot;+xp);

		}
		else
		{
			 Resultat();
		 xp=(Double.parseDouble(txt.getText()));
	
	}
		op=true;mult=false;div=true;som=false;soust=false;YX=false;
		nAr=false;n
Cr=false;X1Y=true;
		}catch(NumberFormatException execp)
    	{
    		txt.set
Background(Color.LIGHT_GRAY);txt.setForeground(Color.RED);
    		txt.setText(&q
uot;ERROR :  CONVERTION  AVEC  VERGULE  FLOTTANTE  NON  SUPPORTEE &quot;);
		  
  activateP2P3(false);}
		}
		////////////////***********Somme**********//////
//////////
		else if(src==bSom)
		{
		try
		{
		if(init || op)
		{
			xs=
(Double.parseDouble(txt.getText()));
			init=false;virg=false;
			txt.setText(
&quot;&quot;+xs);
		}
		else
		{
			 Resultat();
			 xs=(Double.parseDouble
(txt.getText()));
		}
		op=true;mult=false;div=false;som=true;soust=false;YX=f
alse;
		nAr=false;nCr=false;X1Y=true;
		}catch(NumberFormatException execp)
 
   	{
    		txt.setBackground(Color.LIGHT_GRAY);txt.setForeground(Color.RED);

    		txt.setText(&quot;ERROR :  CONVERTION  AVEC  VERGULE  FLOTTANTE  NON  SUPP
ORTEE &quot;);
		    activateP2P3(false);}
		}
		////////////////************
Soustraction***********//////////////////
		else if(src==bSoust)
		{
		try
	
	{
		if(init || op)
		{
			xs=(Double.parseDouble(txt.getText()));
			init=f
alse;virg=false;
			txt.setText(&quot;&quot;+xs);
		}
		else
		{
			Resulta
t();
			xs=(Double.parseDouble(txt.getText()));
		}
	    op=true;mult=false;d
iv=false;som=false;soust=true;YX=false;
	    nAr=false;nCr=false;X1Y=true;
		}
catch(NumberFormatException execp)
    	{
    		txt.setBackground(Color.LIGHT_
GRAY);txt.setForeground(Color.RED);
    		txt.setText(&quot;ERROR :  CONVERTION
  AVEC  VERGULE  FLOTTANTE  NON  SUPPORTEE &quot;);
		    activateP2P3(false);}

	    }
	    //////////////////**************Resultat*************////////////
//////
		else if(e.getSource()==bRes)
		{
			Resultat();
			init=true;virg=f
alse;
		}
		//////////************Les fonction Scientifiques********//////////
///
	 	else if(src==b2ndF)
	 	{shift=true;}
		else if(src==bPuis)
		{
			au
x=Double.parseDouble(txt.getText());
			YX=true;init=false;nAr=false;nCr=false;
X1Y=true;
			op=true;mult=false;div=false;som=false;soust=false;
		}
		else i
f(src==b10x)
		{
			double  x=Double.parseDouble(txt.getText());
			double  r
es=Math.pow(10,x);
			txt.setText(&quot;&quot;+res);
		}
		else if(src==bX2)

		{
			double  x=Double.parseDouble(txt.getText());
			double res=Math.pow(x,
2);
			txt.setText(&quot;&quot;+res);
		}
		else if(src==bX1Y)
		{
		    au
x=Double.parseDouble(txt.getText());
			YX=false;init=false;nAr=false;nCr=false
;X1Y=true;
			op=true;mult=false;div=false;som=false;soust=false;			
		}
		el
se if(src==b1X)
		{
		    double x=Double.parseDouble(txt.getText());
		    i
f(x!=0)
		    {txt.setText(&quot;&quot;+(1/x));}
		    else {txt.setBackground
(Color.LIGHT_GRAY);txt.setForeground(Color.RED);
		    	  txt.setText(&quot; ER
ROR!!  DIVISION  PAR  ZERO  IMPOSSIBLE &quot;);
		          activateP2P3(false)
;}
		}
		else if(src==bLog)
		{
			double  x=Double.parseDouble(txt.getText(
));
			if(!shift &amp;&amp; x&gt;0)
			{
			double  res=Math.log(x);
			txt.
setText(&quot;&quot;+res);
			}
			else if(shift &amp;&amp; x&gt;0)
			{
			
double  res=Math.log10(x);
			txt.setText(&quot;&quot;+res);
			shift=false;	

			}
			else if(x&lt;=0)
			{
				txt.setBackground(Color.LIGHT_GRAY);txt.se
tForeground(Color.RED);
				txt.setText(&quot; ERROR!!  RULE : \&quot;  X  DOIT
  ETRE  &gt;  A  ZERO  \&quot; &quot;);
			    activateP2P3(false);}
		}
		el
se if(src==bEx)
		{
			double  x=Double.parseDouble(txt.getText());
			double
  res=Math.exp(x);
			txt.setText(&quot;&quot;+res);
		}
		else if(src==bFact
)
		{
			
		
			if(isValide(txt.getText()))
			{double res=fact(Double.pars
eDouble(txt.getText()));
			txt.setText(&quot;&quot;+res);}
			else
			{
			
	txt.setBackground(Color.LIGHT_GRAY);txt.setForeground(Color.RED);
				txt.setT
ext(&quot; ERROR!!  RULE :  \&quot;  N  DOIT  ETRE  UN ENTIER  &gt;  A  ZERO \&q
uot; &quot;);
			    activateP2P3(false);}
		}
		else if(src==bSin)
		{
			
if(!shift)
			{
			double  x=Math.toRadians(Double.parseDouble(txt.getText()))
;
		    double res=Math.sin(x);
			txt.setText(&quot;&quot;+res);
			}
			el
se
			{
			double  x=Double.parseDouble(txt.getText());
			double  res=Math.a
sin(x);
			txt.setText(&quot;&quot;+Math.toDegrees(res));
			shift=false;	
		
	}
		}
		else if(src==bCos)
		{
			if(!shift)
			{
			double  x=Math.toRad
ians(Double.parseDouble(txt.getText()));
			double res=Math.cos(x);
			txt.set
Text(&quot;&quot;+res);
			}
			else
			{
			double  x=Double.parseDouble(tx
t.getText());
			double  res=Math.acos(x);
			txt.setText(&quot;&quot;+Math.to
Degrees(res));
			shift=false;	
			}
		}
		else if(src==bTan)
		{
			if(!s
hift)
			{
			double  x=Math.toRadians(Double.parseDouble(txt.getText()));
		
	double res=Math.tan(x);
			txt.setText(&quot;&quot;+res);
			}
			else
			{

			double  x=Double.parseDouble(txt.getText());
			double  res=Math.atan(x);

			txt.setText(&quot;&quot;+Math.toDegrees(res));
			shift=false;	
			}
		}

		else if(src==bSqrt)
		{
			double  x=Double.parseDouble(txt.getText());
		
	if(x&gt;=0)
			{double res=Math.sqrt(x);
			txt.setText(&quot;&quot;+res);}

			else {
				txt.setBackground(Color.LIGHT_GRAY);txt.setForeground(Color.RED);

				txt.setText(&quot; ERROR!!  RULE  :  \&quot;  X  DOIT  ETRE  &gt;  A  ZERO
  \&quot; &quot;);
			    activateP2P3(false);}
		}
		else if(src==bRand)
		
{
			double  x=Double.parseDouble(txt.getText());
			double res=Math.random();

			txt.setText(&quot;&quot;+res);
		}
		else if(src==bnAr)
		{
			aux=Doub
le.parseDouble(txt.getText());
			nAr=true;YX=false;init=false;
			op=true;mul
t=false;div=false;som=false;soust=false;			
		}
			else if(src==bnCr)
		{
		
	aux=Double.parseDouble(txt.getText());
			nCr=true;YX=false;init=false;
			op
=true;mult=false;div=false;som=false;soust=false;			
		}
		/////////**********
**FIN des Fonctions Scientifiques********/////////
	
	    else if(src==bOff) S
ystem.exit(0);
	}
	public void itemStateChanged(ItemEvent i)
	{
		Object src
i=i.getSource();
		if(srci==Scie)
		{
		this.resize(452,564);
		this.getCont
entPane().setLayout(new GridLayout(3,1));
        this.getContentPane().add(pTx
t);this.getContentPane().add(p3);
        this.getContentPane().add(p2); this.s
etLocation(300,100);
        
		}
		else if(srci==Norm)
		{
		//Calculatric
e c=new Calculatrice();
		this.getContentPane().removeAll();
		this.getContent
Pane().setLayout(new GridLayout(2,1));
		this.resize(452,331);
        this.ge
tContentPane().add(pTxt);this.getContentPane().add(p2);
        this.setLocatio
n(300,100);	
        //	c.show();
        //	this.dispose();
		}
		else if(d
ec)
		{
			activateOp(false);
			String dep=txt.getText();
			try
			{
			
String s=fromDec(dep,detBaseDestination(srci));
			txt.setText(s);}
			catch(N
umberFormatException e)
			{
				txt.setBackground(Color.LIGHT_GRAY);txt.setFo
reground(Color.RED);
				txt.setText(&quot;ERROR :  CONVERTION  AVEC  VERGULE  
FLOTTANTE  NON  SUPPORTEE  &quot;);
			    activateP2P3(false);}
		}
		else i
f(bin||oct||hex)
		{
			try
			{
			int x= toDec(txt.getText(),detBaseSource
());
			String s=&quot;&quot;+x;
			txt.setText(fromDec(s,detBaseDestination(s
rci)));}
			catch(NumberFormatException e)
			{
				txt.setBackground(Color.L
IGHT_GRAY);txt.setForeground(Color.RED);
				txt.setText(&quot;ERROR :  CONVERT
ION  AVEC  VERGULE  FLOTTANTE  NON  SUPPORTEE  &quot;);
			    activateP2P3(fal
se);}
		}
	}
	public static void main (String[] args) 
	{
		Calculatrice c=
new  Calculatrice();
	}
}
</pre>
<br /><a name='conclusion'></a><h2> Conclus
ion : </h2>
<br />utilisation simpe.
<br />la plupart des tentative d'erreur 
par l'utilistateur sont prises en charge et elles sont trait&eacute;es.
<br />l
a premire chose &agrave; remarquer c'est que cette calculatrice n'utilise pas le
s parantheses,je souhaite m'aider &agrave; resoudre ce probleme.
<br />le bouto
n 2ndf joue le role du deuxieme fonction seulement pour le cos----&gt;cos-1,sin-
-&gt;sin-1,tan----&gt;tan-1
<br />et ln---&gt;Log
<br />Merci
