# MAF-projekt
Háromszögelő feszítőfák

# Vázlatos matematikai háttér
Alexander Postnikov-nak van egy nagyon meglepő tétele. Ez úgy szól, hogy ha veszünk egy G=(S,T,E) páros gráfot, és megnézzük hogy a feszítőfák hány féle fokszámsorozatot tudnak megvalósítani az S halmazon, és hányat a T-n, akkor ezeknek a száma mindig egyenlő. Vegyük például a K_4,2 teljes páros gráfot. Itt a 2 pontú osztályon a (4,1);(3,2);(2,3);(1,4) fokszámsorozatok valósíthatók meg (a (4,1) és az (1,4) négyféleképpen, a másik kettő pedig 12-féleképpen), a 4 pontú osztályon pedig a (2,1,1,1);(1,2,1,1);(1,1,2,1);(1,1,1,2) fokszámsorozatok (mindegyik 8-féleképpen). Látjuk, hogy mindkét esetben 4 lehetséges fokszámsorozat van, de egyáltalán nem világos hogy mi ennek az oka, vagy hogyan lehetne őket bijekcióba rakni. Postnikov egy nagyon szép geometriai bizonyítást adott erre az eredményre. Megmutatta hogy a gráfhoz hozzá lehet rendelni egy politópot, aminek a csúcsai a gráf éleinek felelnek meg, és néhány csúcs pontosan akkor határoz meg maximális dimenziós szimplexet, ha a megfelelő részgráf egy feszítőfa. Majd megmutatta, hogy ha a politópot belsőleg diszjunkt szimplexekre bontjuk, akkor a szimplexeknek megfelelő feszítőfa halmaz bijekciót ad az S-en és a T-n megvalósítható fokszámsorozatok között. Az ilyen feszítőfa halmazokat nevezzük háromszögelőnek.

(Postnikov, Alexander. Permutohedra, associahedra, and beyond. Int. Math. Res. Not. IMRN 2009, no. 6, 1026--1106.)

# Mit csinál a program?
A célom az volt, hogy a program segítségével kicsit jobban megérthessük a háromszögelő feszítőfa halmazokat. A program egy (vagy több) inputként kapott páros gráfra megkeresi és (kék színnel) kirajzolja, hogy a feszítőfáinak mely részhalmazai alkotnak háromszögelést. A háromszögelések közül kiválogatja, és más színnel (pirossal) színezi azokat, amelyek bizonyos értelemben szép, úgynevezett reguláris háromszögelések. Ezen kívül azt is megvizsgálja a gráf minden feszítőfájára, hogy az adott fa hány háromszögelésben szerepel, és ezeket is kirajzolja, feltüntetve a gyakoriságukat is.

# Hogyan futtassuk?
A programot a main függvény segítségével kell futtatni, amelynek argumentumai, és ezek jelentése:

  filename: a txt file neve, amely az input gráfokat tartalmazza
  
  draw: 1 --> kirajzolja a háromszögelő halmazokat, 0 --> nem rajzolja ki a háromszögelő halmazokat
        
  distr: 1 --> kirajzolja a feszítőfákat az előfordulási gyakoriságuk szerint, 0 --> nem rajzolja ki a feszítőfákat az előfordulási gyakoriságuk szerint
         
  reg: 1 --> pirosra színezi a reguláris halmazokat, amennyiben draw=1, 0 --> nem színezi pirosra a reguláris halmazokat
       
A program létrehoz almappákat a program file-t is tartalmazó mappába, és ezekbe rendezi az outputként kapott ábrákat.
       
# Példa
main("pelda.txt", 1, 1, 1)

    pelda.txt:
        K_3,3 - e
        3 3
        [(0,0),(0,1),(0,2),(1,0),(1,1),(1,2),(2,0),(2,1)]
        K_3,3 - cseresznye
        3 3
        [(0,0),(0,1),(0,2),(1,0),(1,1),(1,2),(2,0)]
        
 output file-ok:
 
    "distribution_pelda.txt_0" (első gráf feszítőfái és gyakoriságuk)
    
    "distribution_pelda.txt_1" (második gráf feszítőfái és gyakoriságuk)
    
    "triangulations_pelda.txt_0" (első gráf háromszögelő halmazai, pirossal jelölve a regulárisak)
    
    "triangulations_pelda.txt_1" (második gráf háromszögelő halmazai, pirossal jelölve a regulárisak)
