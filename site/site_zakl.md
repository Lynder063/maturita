# Počítačové sítě - základní pojmy a topologie

## Počítačová síť:
  - Je systém, který vzniká vzájemným propojením zařízení s cílem komunikace.
  - Základním důvodem pro vytvoření prvních sítí byla potřeba společného přístupu k datům a využití jiného počítače.
  - Síť se skládá
    - jednotlivých *(stanic)*
    - síťového hardwaru *(síťové karty, aktivní a pasivní síťové prvky)*  
    - síťového softwaru.
  - Osoba, která dohlíží na zapojení počítačové sítě je správce sítě. Má přehled i o uživatelích a jejích právech.
  - Jsou dva typy komunikace
    - **Klient / server**
      * Komunikace **klient-server**, server, který poskytuje ostatním stanicím služby jako jsou souborové, aplikační nebo databázové služby. Pracovní stanice, u které pracuje uživatel a využívá služeb které poskytuje server.
      * Základní rozdělení sítě jsou klient-server *(síť serverového typu, je to síť s centralizovanými prostředky, skládá se z hlavního počítače a pracovních stanic jejichž počet je závislý na výkonnosti serveru. Slouží ke správě sítě a uložení společných dat)*
    - **Peer-to-peer**
      * **Peer-to-peer** *(je to síť s distribuovanými prostředky a není určen server, všechny počítače si jsou rovny, využívá se jako jednoduchá pracovní síť obvykle kolem 10 stanic, pokud je množství počítačů větší, udržuje se špatně přehled o prostředcích které jsou k dispozici, hlavně datové soubory a programy. Všechny počítače musí zůstat zapnuty dokud poslední uživatel neukončí práci s příslušným sdíleným prostředkem.)*

- Rozdělení sítí dle velikosti:
  - **LAN** *(lokální síť – ve firmách a školách)*  
  - **MAN** *(městské sítě)*  
  - **WAN** *(rozsáhlé národní až celosvětové sítě – Internet)* sítě  



- **Výhody / Nevýhody**
  - **Výhody**
      - sdílení prostředků - data, tiskárny nebo programy (Výhody jsou úspora místa na disku, techniky)
      - Centralizovaná správa
      - Zálohování
      - Rychlá výměna informací
  - **Nevýhody**
      - Bezpečnost
      - Práce



### Topologie sítě:  
představují způsoby rozmístění a spoluprací počítačů zapojených v síti.  

- Jsou dva typy:
    1. topologie fyzická (způsob propojení stanic v síti)
    2. topologie logická (způsob komunikace v síti)  



**Topologie dělíme na**

Sběrnicová topologie:<br>

![NetworkTopology-Bus](https://user-images.githubusercontent.com/56117532/168580650-b8fcad9d-022b-4340-a093-fb24abbb7905.png)<br>

(nejjednodušší a nejlevnější, každá stanice je připojena ke společnému kabelu který tvoří základ sítě. Výhody – nízká spotřeba kabelu a nízké náklady, porucha jedné stanice nemá vliv na ostatní. Nevýhody – koaxiální kabel je náchylný k mechanickému poškození, obtížná lokalizace závad, porucha na sběrnici vyřadí z funkce celou síť.)  

BNC konektory, T-konektory, Terminátory

    + Snadná realizace a snadné rozšíření jíž stávající sítě.
    + Nevyžaduje tolik kabeláže jako např. hvězdicová topologie.
    + Vhodná pro malé nebo dočasné sítě, které nevyžadují velké rychlosti přenosu.

    - Nesnadné odstraňování závad.
    - Omezená délka kabelu a také počtu stanic.
    - Pokud nastane nějaký problém s kabelem, celá síť přestane fungovat.
    - Výkon celé sítě rapidně klesá při větších počtech stanic nebo při velkém provozu.



Hvězdicová topologie:<br>
![Hvězdicová_topologie](https://user-images.githubusercontent.com/56117532/168581419-5b35c3d3-7bf0-4404-adbc-fb4ad68d2947.png)<br>

propojuje stanice **aktivním prvkem switch**, její úkolem je směrovat data zaslaná z jedné stanice k ostatním. K propojení stanic switchem se používá **kroucená dvojlinka**. *(T-konektor nebo terminator se nepoužívá!!)* 

    + Pokud selže jeden počítač nebo kabel, nebude fungovat spojení pouze pro jednu stanici a ostatní stanice mohou vysílat i přijímat nadále.
    + Dobrá výkonnost v porovnání se sběrnicovou topologií. To souvisí s tím, že na jednom kabelu je připojen pouze jeden počítač a tudíž jednak nedochází ke kolizím mezi pakety a také může současně přenášet data více počítačů.
    + Snadno se nastavuje a rozšiřuje.
    + Závady se dají snadno nalézt.

    - U větších sítí vyžadováno velké množství kabelů - ke každému počítači jeden.
    - Potřeba extra hardware v porovnání se sběrnicovou topologií.
    - V případě selhání centrálního síťového prvku přestane fungovat celá síť.

Kruhová topologie:<br>
![obrazek](https://user-images.githubusercontent.com/56117532/168581611-ee2efa8f-618a-4a55-8c21-72bc19f8a0b3.png)<br>

    + přenos dat je poměrně jednoduchý, protože pakety se posílají jedním směrem
    + přidání dalšího uzlu má jen malý dopad na šířku pásma
    + nevznikají kolize
    + minimální zpoždění (v bitech podle počtu uzlů)
    + průchodnost sítě je z výše uvedených důvodů ze všech ostatních topologií nejvyšší
    + snadná možnost implementace záruk na množství přenesených dat za jednotku času
    + množství kabelů může být menší, než u hvězdicové topologie
    
    - vstup a výstup (zapnutí a vypnutí) stanice je logicky a implementačně komplikovaná operace
    - data musí projít přes všechny členy kruhu, což zvyšuje riziko poruchy
    - přerušením kruhu vzniká problém (při vyřazení jedné stanice přestávají pracovat další stanice)
    - při přidání nového uzlu je nutné dočasně kruh přerušit (u Token ringu jen na zanedbatelný okamžik)

Stromová topologie / Hybridní topologie:<br>
![obrazek](https://user-images.githubusercontent.com/56117532/168581885-c1a6db75-a2f5-421c-be41-d5b44b137e4f.png)<br>

je tvořena kombinací hvězdicové a sběrnicové topologie. Jejím základem je páteřní vedení ke kterému se připojují další části. Páteřní vedení je segment sítě ke kterému jsou připojeny ostatní segmenty. 

    + Pokud selže jeden aktivní síťový prvek, ostatní části sítě mohou dále pokračovat.
    + Snižuje se potřebné množství kabelů.
    + Zvýšení bezpečnosti – zvyšuje se obtížnost odposlouchávání síťové komunikace. (Pv11)
