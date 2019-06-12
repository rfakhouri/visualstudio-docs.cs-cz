---
title: Získávání začít s vytvářením her pomocí Unity v sadě Visual Studio pro Mac
description: Začínáme s Unity a Visual Studio pro Mac
author: asb3993
ms.author: amburns
ms.date: 05/20/2019
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: D07FA43B-9D18-4DFA-8343-CD538FAD84DB
ms.openlocfilehash: 8f14d21468336dba220a76ad8978f136d50f96f1
ms.sourcegitcommit: cc5fd59e5dc99181601b7db8b28d7f8a83a36bab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2019
ms.locfileid: "66836395"
---
# <a name="getting-started-building-games-with-unity-in-visual-studio-for-mac"></a>Získávání začít s vytvářením her pomocí Unity v sadě Visual Studio pro Mac 

Je herní engine, která umožňuje vývoj her v Unity C#. Tento návod ukazuje, jak začít s vývojem a ladění her Unity pomocí sady Visual Studio pro Mac a Visual Studio for Mac Tools pro Unity rozšíření spolu s prostředí Unity.

Visual Studio for Mac Tools for Unity je bezplatné rozšíření, instalace sady Visual Studio pro Mac. Umožňuje vývojářům Unity využít výhod funkcí produktivitu sady Visual Studio pro Mac, včetně skvělou podporu technologie IntelliSense, ladění a další funkce.

## <a name="objectives"></a>Cíle

> [!div class="checklist"]
> * Další informace o vývoji pro Unity pomocí sady Visual Studio for Mac

## <a name="prerequisites"></a>Požadavky

- Visual Studio for Mac ([https://www.visualstudio.com/vs/mac](https://www.visualstudio.com/vs/visual-studio-mac))
- Unity 5.6.1 osobní Edition nebo vyšší ([https://store.unity.com](https://store.unity.com/), vyžaduje účet unity.com ke spuštění)

## <a name="intended-audience"></a>Cílová skupina

Toto testovací prostředí je určeno pro vývojáře, kteří znají C#, i když prostředí není potřeba.

## <a name="task-1-creating-a-basic-unity-project"></a>Úkol 1: Vytvoření základního projektu Unity

1. Spuštění **Unity**. Přihlaste, pokud o to požádá.

2. Klikněte na možnost **Nové**.

    ![Tlačítka Nový v unity](media/unity-image1.png)

3. Nastavte **název projektu** k **"UnityLab"** a vyberte **3D**. Klikněte na tlačítko **vytvořit projekt**.

    ![Vytvoření obrazovky nového projektu](media/unity-image2.png)

4. Nyní se díváte na výchozí rozhraní Unity. Má hierarchie scény s herním objektům na levé straně, 3D zobrazení prázdné scény zobrazí uprostřed podokno soubory projektu v dolní části a inspector a služeb na pravé straně. Samozřejmě je k němu mnohem větší než největší, ale pár důležitých komponent jsou.

    ![rozhraní prázdné unity](media/unity-image3.png)

5. Pro vývojáře Unity začínáte, všechno, co se spouští v aplikaci bude existovat v rámci kontextu **scény**. Soubor scény je jeden soubor, který obsahuje všechny možné druhy metadata o prostředcích využívaných v projektu pro aktuální scény a její vlastnosti. Když vytvoříte balíček aplikace pro platformu, výsledná aplikace se ukončí nebuďte kolekce jednoho nebo více scény a navíc všechny kódu závislého na platformě, které přidáte. Můžete mít libovolný počet scén podle potřeby v projektu.

6. Novou scénu právě obsahuje kamera a směrové světlo. Vyžaduje scény **fotoaparát** pro všechno, co uvidí a **naslouchací proces zvuk** pro všechno, co slyšitelné. Tyto součásti jsou připojeny k **GameObject**.

7. Vyberte **hlavní fotoaparát** objektu z **hierarchie** podokně.

    ![v podokně hierarchie zvýrazní objektu hlavní fotoaparátu](media/unity-image4.png)

8. Vyberte **inspektoru** podokně z pravé strany okna, které se podívejte na její vlastnosti. Fotoaparát vlastnosti zahrnují informace o transformaci, pozadí, typ projekce, pole zobrazení a tak dále. Jako součást zvuku naslouchacího procesu se taky přidala ve výchozím nastavení, která v podstatě vykreslí zvuk scény z virtuální mikrofonu připojené k fotoaparátu.

    ![Podokno inspektoru](media/unity-image5.png)

9. Vyberte **směrové světlo** objektu. To poskytuje světlo do scény, komponenty, jako jsou shadery věděli, jak lze vykreslit objekty.

    ![Směr světla objekt zvýrazněnou](media/unity-image6.png)

10. Použití **inspektoru** zobrazíte, že obsahuje běžné vlastnosti osvětlení, včetně typu, barvy, intenzita, stín typu a tak dále.

    ![ve vlastnosti v inspektoru podokno](media/unity-image7.png)

11. Je důležité zdůraznit, že se trochu liší od jejich Visual Studio for Mac protějšky projektů Unity. V **projektu** karta v dolní části klikněte pravým tlačítkem myši **prostředky** a pak zvolte položku **zobrazit ve Finderu**.

    ![Zobrazit ve Finderu kontext akce](media/unity-image8.png)

12. Projekty obsahují **prostředky**, **knihovny**, **ProjectSettings**, a **Temp** složek můžete vidět. Je však pouze jeden, který se zobrazuje v rozhraní **prostředky** složky. **Knihovny** složky se o místní mezipaměti pro importované prostředky; obsahuje všechna metadata pro prostředky. **ProjectSettings** složky ukládá nastavení můžete nakonfigurovat. **Temp** složky se používá pro dočasné soubory z Mono a Unity během procesu sestavení. Je také soubor řešení, které můžete otevřít v sadě Visual Studio pro Mac (**UnityLab.sln** tady).

    ![prostředky ve Finderu.](media/unity-image9.png)

13. Zavřít **Finder** okno a vraťte se do **Unity**.

14. **Prostředky** složka obsahuje všechny vaše prostředky moderní kód, zvuk, atd. Je teď prázdný, ale místo pro každý soubor, který se zapojit do vašeho projektu. Toto je vždy na složku nejvyšší úrovně v **Unity Editor**. Ale vždy přidat a odebrat soubory prostřednictvím rozhraní Unity (nebo sady Visual Studio pro Mac) a nikdy prostřednictvím systému souborů přímo.

    ![Složka prostředků v unity](media/unity-image10.png)

15. **GameObject** je zásadním pro vývoj v Unity téměř vše, co je odvozen od typu, včetně modelů, světla, systémy a tak dále. Přidat nový **datové krychle** objekt na scéně prostřednictvím **GameObject > 3D objektu > datové krychle** nabídky.

    ![Datová krychle objekt na scéně](media/unity-image11.png)

16. Rychle zkontrolovat ve vlastnostech nového **GameObject** a podívejte se, že má název, značky, vrstvy a transformace. Tyto vlastnosti jsou společné pro všechny **GameObjects**. Kromě toho několik komponent byla připojena ke **datové krychle** zajistit potřebné funkce včetně mřížky filtr, kolidující objekt pole a nástroj pro vykreslování.

    ![vlastnosti objektu](media/unity-image12.png)

17. Přejmenovat **datové krychle** objektu, který má název **"Datová krychle"** ve výchozím nastavení, na **"Nepřítele"** . Ujistěte se, že stisknutím klávesy **Enter** uložte změnu. Bude jím nepřátelský datové krychle v našich jednoduché hře.

    ![Vlastnosti přejmenování objektu datové krychle](media/unity-image13.png)

18. Přidejte další **datové krychle** objekt na scéně pomocí stejných postupů, jak je uvedeno výše a název tohoto **"Player"** .

    ![Přejmenujte druhý objekt datové krychle](media/unity-image14.png)

19. Označení objektu player **"Player"** také (naleznete v tématu **značka** ovládací prvek rozevírací přímo pod pole s názvem). Použijeme v nepřátelský skript pro usnadnění vyhledání objektu player her.

    ![označení objektu player](media/unity-image15.png)

20. V **scény** zobrazení, přesunout objekt player od nepřátelský objektu na ose Z pomocí myši. Můžete přesunout na ose Z výběrem a přetažením datové krychle podle jeho **red** panelu směrem k **modré** řádku. Protože se nachází v 3D prostoru datové krychle, ale lze pouze táhnout ve formě 2D pokaždé, když, osy, na kterém přetažení je obzvláště důležité.

    ![Datová krychle zobrazující zobrazení scény](media/unity-image16.png)

21. Datová krychle přesuňte dolů a doprava na ose. Tím se aktualizuje **Transform.Position** vlastnost **inspektoru**. Ujistěte se, že přetáhnout na umístění podobně a co je znázorněno zde pro usnadnění pozdější kroky v testovacím prostředí.

    ![Přesunutí jednu datovou krychli na ose](media/unity-image17.png)

22. Nyní můžete přidat nějaký kód Centrum umožňující prosazovat nepřátelský logiky tak, aby sleduje přehrávač. Klikněte pravým tlačítkem na **prostředky** složky **projektu** panel a vyberte **vytvořit > C# skript**.

    ![C#kontext akce skriptu](media/unity-image18.png)

23. Pojmenujte novou C# skript **"EnemyAI"** .

    ![Skript jazyka C#](media/unity-image19.png)

24. Připojit skripty, které herním objektům, přetáhněte nově vytvořený skript do **nepřítele** objekt **hierarchie** podokně. Nyní tento objekt se bude používat chování z tohoto skriptu.

    ![zvýraznění znázorňující přidávání skriptů do objektu](media/unity-image20.png)

25. Vyberte **soubor > Uložit scén** uložit aktuální scény. Pojmenujte ji **"MyScene"** .

## <a name="task-2-working-with-visual-studio-for-mac-tools-for-unity"></a>Úkol 2: Pracovat se službou Visual Studio for Mac Tools for Unity

1. Nejlepší způsob, jak upravit C# kód je pomocí sady Visual Studio pro Mac. Můžete nakonfigurovat Unity pomocí sady Visual Studio pro Mac jako jeho výchozí obslužnou rutinu. Vyberte **Unity > Předvolby**.

2. Vyberte **externích nástrojů** kartu. Z **externí Editor skriptů** rozevíracího seznamu vyberte **Procházet** a vyberte **aplikací/Visual Studio.app**. Případně pokud už existuje **sady Visual Studio** možnost, stačí vybrat, který.

    ![na kartě Předvolby externí nástroje](media/unity-image21.png)

3. Unity je teď nakonfigurovaná na použití **Visual Studio for Mac** pro úpravu skriptu. Zavřít **Unity Předvolby** dialogového okna.

    ![Vybraný v předvolbách sady Visual Studio](media/unity-image22.png)

4. Dvakrát klikněte na panel **EnemyAI.cs** a otevřete tak **Visual Studio for Mac**.

    ![Nepřátelský asset vybrané v unity](media/unity-image23.png)

5. Řešení sady Visual Studio je jednoduché. Obsahuje **prostředky** složka (na jeden z **Finder**) a **EnemyAI.cs** skript vytvořený dříve. V projektech pro složitější bude vypadat hierarchii pravděpodobně jiná než uvidíte v Unity.

    ![Oblasti řešení v sadě Visual Studio pro Mac](media/unity-image24.png)

6. **EnemyAI.cs** je otevřen v editoru. Počáteční skript právě obsahuje zástupné procedury **Start** a **aktualizace** metody.

7. Počáteční nepřátelský kódu nahraďte následujícím kódem.

    ```csharp
    public class EnemyAI : MonoBehaviour
    {
        public float Speed = 50;
        private Transform _playerTransform;
        private Transform _myTransform;
        
        void Start()
        {
            var player = GameObject.FindGameObjectWithTag("Player");
            if (!player)
            {
                Debug.LogError(
                    "Could not find the main player. Ensure it has the player tag set.");
            }
            else
            {
                _playerTransform = player.transform;
            }
            _myTransform = this.transform;
        }

        void Update()
        {
            var moveAmount = Speed * Time.deltaTime;
            _myTransform.position = Vector3.MoveTowards(_myTransform.position,
                _playerTransform.position, moveAmount);

            if (_myTransform.position == _playerTransform.position)
            {
                _myTransform.position = Vector3.back * 10;
            }
        }
    }
    ```

8. Rychlý pohled na jednoduché nepřátelský chování, které je definováno zde trvat. V **Start** metody jsme získáte odkaz k objektu player (podle jeho značky), stejně jako jeho **transformace**. V **aktualizace** metodu, která se volá u každého snímku, nepřítele se přesuňte směrem k objektu player. Klíčová slova a názvy využívají barevné kódování, aby bylo snazší porozumět základu kódu v sadě Visual Studio pro Mac.

9. Uložte změny do nepřátelský skript v **Visual Studio for Mac**.

## <a name="task-3-debugging-the-unity-project"></a>Úkol 3: Ladění projektů Unity

1. Nastavit zarážku na prvním řádku kódu **Start** metoda. Můžete buďto kliknout na okraj editoru na cílový řádek nebo místo kurzor na řádku a stisknutím klávesy **F9**.

    ![Nastavení zarážky v sadě visual studio pro mac](media/unity-image25.png)

2. Klikněte na tlačítko **spustit ladění** tlačítko nebo stisknutím klávesy **F5**. Tím se projekt sestavil a připojit k Unity pro ladění.

    ![tlačítko Start v sadě visual studio pro mac](media/unity-image26.png)

3. Vraťte se na **Unity** a klikněte na tlačítko **spustit** tlačítko hru.

    ![tlačítko pro spuštění v unity](media/unity-image27.png)

4. By měla být zarážka dosažena a můžete teď použít Visual Studio pro Mac ladicích nástrojů.

    ![Zarážka přístupů v sadě visual studio pro mac](media/unity-image28.png)

5. Z **místní hodnoty** vyplnění, vyhledejte **to** ukazatel, který odkazuje **EnemyAI** objektu. Rozbalte odkaz a podívejte se, že můžete procházet přidružené členy jako **rychlost**.

    ![místní ladění panel v sadě visual studio pro mac](media/unity-image29.png)

6. Odebrat narážku z **Start** metoda stejným způsobem, který byl přidán – tím, že kliknete na okraji nebo výběrem řádku a stisknutím klávesy **F9**.

    ![Zarážka přístupů v sadě visual studio pro mac](media/unity-image30.png)

7. Stisknutím klávesy **F10** krok přes první řádek kódu, který najde **Player** objektu tagu jako parametr.

8. Najeďte myší do přes **player** proměnné v rámci okna editoru kódu pro zobrazení přidružené členů. Můžete dokonce rozšířit překrytí, chcete-li zobrazit vlastnosti podřízené.

    ![ladění okna v sadě visual studio pro mac editoru](media/unity-image31.png)

9. Stisknutím klávesy **F5** nebo stiskněte klávesu **spustit** tlačítko pro pokračování v provádění. Vrátit se k Unity zobrazíte nepřátelský datové krychle opakovaně přístup player datové krychle. Budete muset upravit fotoaparátu/kamery, pokud není viditelná.

    ![scény přehrávání v unity](media/unity-image32.png)

10. Přepněte zpátky na **Visual Studio for Mac** a nastavte zarážku na prvním řádku **aktualizace** metoda. By měl bezprostředně přístupů.

    ![nastavením zarážky v sadě visual studio pro mac](media/unity-image33.png)

11. Předpokládejme, že je příliš rychle rychlost a chceme otestovat závažnosti dopadu změn bez restartování aplikace. Vyhledejte **rychlost** proměnné v rámci **automatické hodnoty** nebo **lokální** okno a potom změňte ho na **"10"** a stiskněte klávesu **Enter** .

    ![Úprava proměnné v okně místních hodnot](media/unity-image34.png)

12. Odebrat zarážku a stisknutím klávesy **F5** pokračovat provádění.

13. Vraťte se na **Unity** k běžící aplikaci zobrazit. Nepřátelský datové krychle se momentálně přesouvají na páté původní rychlosti.

    ![okno Unity se spouštěním aplikací](media/unity-image35.png)

14. Zastavit aplikaci Unity po kliknutí **Přehrát** tlačítko znovu.

    ![Zastavuje se aplikace unity](media/unity-image36.png)

15. Vraťte se na **Visual Studio for Mac**. Zastavit relaci ladění kliknutím **Zastavit** tlačítko.

    ![Zastavuje se relace ladění v sadě Visual Studio pro Mac](media/unity-image37.png)

## <a name="task-4-exploring-unity-features-in-visual-studio-for-mac"></a>Úloha 4: Prozkoumání funkcí Unity v sadě Visual Studio pro Mac

1. Visual Studio pro Mac nabízí rychlý přístup k dokumentaci k Unity v editoru kódu. Umístěte kurzor někam na **Vector3** symbolů v rámci **aktualizace** metodu a stiskněte klávesu **⌘ příkaz + "** .

    ![Výběr metody v sadě visual studio pro mac editoru](media/unity-image38.png)

2. Otevře se nové okno prohlížeče v dokumentaci k **Vector3**. Zavřete okno prohlížeče, když vyhovují.

    ![Otevře se okno prohlížeče na dokumentaci](media/unity-image39.png)

3. Visual Studio pro Mac také poskytuje několik pomocných rutin můžete rychle vytvořit třídy chování Unity. Z **Průzkumníka řešení**, klikněte pravým tlačítkem na **prostředky** a vyberte **Přidat > Nová třída MonoBehaviour**.

    ![Nová třída monobehaviour kontext akce](media/unity-image40.png)

4. Nově vytvořené třídy obsahuje zástupné procedury **Start** a **aktualizace** metody. Za pravou závorku **aktualizace** metody, začněte psát **"onmouseup"** . Jak budete zadávat, Všimněte si, aby IntelliSense ve Visual Studio rychle nuly v na metodu, kterou plánujete implementovat. Vyberte ho ze seznamu zadaná automatické dokončování. Je pro vás, včetně všech parametrů vyplní pahýl metody.

    ![technologie IntelliSense v sadě visual studio pro mac](media/unity-image41.png)

5. Uvnitř **OnMouseUp** typ, metodu **"základní".** Pokud chcete zobrazit všechny základní metody, které jsou k dispozici k volání. Můžete také prozkoumat různé přetížení jednotlivých funkcí pomocí možnosti stránkování v pravém horním rohu informační rámeček technologie IntelliSense.

    ![zkoumání přetížení v sadě visual studio pro mac](media/unity-image42.png)

6. Visual Studio pro Mac také umožňuje snadno definovat nové shadery. Z **Průzkumníka řešení**, klikněte pravým tlačítkem na **prostředky** a vyberte **Přidat > Nová třída Shader**.

    ![Nová akce shaderu v sadě visual studio pro mac](media/unity-image43.png)

7. Formát souboru shaderu získá úplnou barev a písma zacházení usnadňují čtení a pochopení.

    ![Zvýrazňování syntaxe](media/unity-image44.png)

8. Vraťte se na **Unity**. Uvidíte, že vzhledem k tomu, že Visual Studio pro Mac spolupracuje s stejný systém projektu, změny provedené na jednom místě jsou automaticky synchronizovat s druhou. Teď můžete snadno vždy používat vždycky ten nejlepší nástroj pro úlohu.

    ![panel aktiva Unity](media/unity-image45.png)

## <a name="summary"></a>Souhrn

V tomto testovacím prostředí jste zjistili, jak začít, vytvoření hry s Unity a Visual Studio pro Mac. Zobrazit [ https://unity3d.com/learn ](https://unity3d.com/learn) získat další informace o Unity.
