---
title: Pomocí nástrojů Visual Studio Tools for Unity | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: e67ec9a2-a449-413e-8930-9a471bd43a06
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: c0300e26c8811dc877ad6d01e1afbc5ef6ca35df
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31068985"
---
# <a name="using-visual-studio-tools-for-unity"></a>Používání sady Visual Studio Tools for Unity
V této části se dozvíte, jak používat Visual Studio Tools for Unity na integrace a funkce produktivitu a používání ladicího programu sady Visual Studio pro vývoj Unity.

## <a name="unity-integration-and-productivity"></a>Integrace Unity a produktivitu
 Visual Studio Tools for Unity se integruje s editoru Unity můžete zvýšit produktivitu. Tyto funkce rozšíření produktivitu automatizaci běžných úkolů skriptování a přenést informace z Unity do sady Visual Studio tak, že nemáte, přejděte do editoru Unity ho najít.

### <a name="unity-documentation-access"></a>Přístup k dokumentaci Unity
 Můžete přistupovat Unity skriptování dokumentace rychle ze sady Visual Studio. Pokud Visual Studio Tools for Unity nenalezne dokumentaci rozhraní API místně, pokusí se najít online.

##### <a name="to-access-unity-documentation"></a>Pro přístup k dokumentaci Unity

-   V sadě Visual Studio, zvýrazněte nebo umístěte kurzor přes rozhraní API Unity chcete další informace o a poté stiskněte klávesu **Ctrl + Alt + M, Ctrl + H**

### <a name="unity-monobehavior-scripting-wizard"></a>Průvodce skriptování MonoBehavior Unity
 V Unity Většina skriptů jsou implementované odvozování od třídy MonoBehavior a přepsáním některé její metody. Průvodce MonoBehavior můžete rychle vytvořit prázdný definice, které chcete přetížení metody MonoBehavior. Pomocí tohoto průvodce, můžete zadat jednu nebo více metod, které chcete přetížení ze seznamu dostupných metod, zvolte, kde se vloží do kódu a rozhodnout, zda chcete-li zahrnout komentáře o tom, jak se používají.

 ![Dialogové okno Průvodce monobehavior. ] (../cross-platform/media/vstu_monobehavior_wizard_full.png "vstu_monobehavior_wizard_full")

##### <a name="to-create-empty-monobehavior-method-definitions-by-using-the-monobehavior-wizard"></a>K vytvoření definice metoda prázdný MonoBehavior pomocí Průvodce MonoBehavior

1.  V sadě Visual Studio, umístěte kurzor může místo metody vložit, a pak stiskněte klávesu **Ctrl + Shift + M** spusťte Průvodce MonoBehavior. Nebo, pokud chcete k vložení nové metody za ten, který je již byla implementována, můžete určit, že novější. Stačí stisknout klávesu **Ctrl + Shift + M**.

2.  Vyberte metodu, kterou chcete přetížení. V **vytvořit skript metody** okno, v části **výběr metod vytvoření**, označte zaškrtávací políčko vedle názvu každé metody, kterou chcete přetížení.

3.  Zajistěte, aby verze rozhraní framework zobrazí v **Framework, verze** rozevírací odpovídá verzi používáte. Pokud neodpovídá, změňte hodnotu z rozevíracího seznamu na verzi, kterou chcete použít.

4.  Zvolte, budou vloženy metody. Ve výchozím nastavení jsou metody vloženy na pozici kurzoru; Pokud chcete vložit je někde jinde, můžete je vložení za libovolné metody, která je již implementována ve třídě. Vyberte jednu z těchto umístění, změňte hodnotu z **kurzor** rozevírací dolů do umístění, které chcete.

5.  Pokud chcete, aby průvodce generovat komentáře pro metody, které jste vybrali, označte **generovat metoda komentáře** zaškrtávací políčko. Tyto komentáře jsou určené vám pomohou pochopit, když je volána metoda a jaké jsou jeho obecné odpovědnosti.

6.  Vyberte **OK** tlačítko Ukončit průvodce a vkládání metody do vašeho kódu.

 Průvodce MonoBehavior je užitečná zejména při stále seznamování rozhraní API Unity, nebo když potřebujete přetížení metody, které si nejste obeznámeni s. Až se více zkušenosti s rozhraním API pro Unity, možná budete chtít rychle MonoBehavior Průvodce pro rychlé vytvoření metody, které jste již obeznámeni s.

#### <a name="quick-monobehavior-scripting-wizard"></a>Rychlé MonoBehavior skriptování průvodce
 Pokud jste již obeznámeni s rozhraním API pro Unity, můžete implementovat přetížené metody i rychleji pomocí rychlé MonoBehavior průvodce. Pomocí tohoto průvodce, můžete zadat pouze jednu metodu, která je vložen bez metoda komentáře v umístění kurzoru.

 ![Dialogové okno rychlé monobehavior průvodce. ] (../cross-platform/media/vstu_monobehavior_wizard_quick.png "vstu_monobehavior_wizard_quick")

###### <a name="to-create-an-empty-monobehavior-method-definition-by-using-the-quick-monobehavior-wizard"></a>Vytvoření definice metoda prázdný MonoBehavior pomocí Průvodce rychlé MonoBehavior

1.  V sadě Visual Studio, umístěte kurzor místo metodu vložit, a pak stiskněte klávesu **Ctrl + Shift + Q** spusťte Průvodce rychlé MonoBehavior. Na rozdíl od jiných MonoBehavior průvodce musíte umístěte kurzor záměrně při použití tohoto průvodce vzhledem k tomu, že je nová metoda vždycky vložit existuje.

2.  Zajistěte, aby verze rozhraní framework zobrazí v pravém horním rohu **vytvořit skript metoda** okno odpovídá verzi používáte. Pokud neodpovídá, změňte hodnotu z rozevíracího seznamu na verzi, kterou chcete použít.

3.  Find – metoda, kterou chcete přetížení. V okně vytvořit skript metoda začněte psát název metody, do textového pole. Zobrazí se seznam metod, jejichž názvy shodovat, co jste zadali.

4.  Zvolte metodu, kterou chcete přetížení. Pokud chcete, aby metoda se zobrazí v seznamu, vyberte ho pomocí myši nebo šipku kláves, stiskněte **Enter**. Pokud je jedinou metodou v seznamu, můžete stačí stisknout **Enter**. Metoda budou vložena do vašeho kódu.

### <a name="unity-project-explorer"></a>Unity Project Exploreru
 Můžete Unity Project Exploreru přejděte Unity projektu v sadě Visual Studio.

 ![Okno Prohlížeč projektu Unity. ] (../cross-platform/media/vstu_unity_project_explorer.png "vstu_unity_project_explorer")

##### <a name="to-view-the-unity-project-explorer"></a>Chcete-li zobrazit Project Exploreru Unity

-   V sadě Visual Studio v hlavní nabídce zvolte **zobrazení**, **Unity Project Exploreru**. Klávesové: **Alt + Shift + E**

     ![Zobrazte okno Unity Project Exploreru. ] (../cross-platform/media/vstu_view_unity_project_explorer.png "vstu_view_unity_project_explorer")

 Zobrazuje všechny soubory projektu Unity a adresáře Project Exploreru Unity stejným způsobem, který nemá editoru Unity – to je jiné než navigace unity skripty pomocí Průzkumníka řešení, která obsahuje jenom váš skript soubory a zobrazují se jako projekty a řešení generované Visual Studio Tools for Unity uspořádá je. Zejména u velkých projektů je často usnadní vyhledání skriptu, který chcete upravit pomocí Unity Project Exploreru; také umožňuje snadno upravit jiné typy souborů – například textové konfigurační soubory – v sadě Visual studio bez jejich přidáním do jednoho z projektů v sadě Visual Studio řešení.

### <a name="unity-error-list"></a>Seznam chyb Unity
 Zprávy z konzoly Unity v sadě Visual Studio můžete zobrazit, když je připojen k instanci Unity. To zahrnuje chyby a upozornění z Unity. Zprávy se zobrazují v sadě Visual Studio **seznam chyb** okno; Chyba zprávy z Unity se zobrazují na **chyby** kartě zprávy upozornění na **upozornění** kartě a další zprávy – například zprávy odeslané přes Debug.Log Unity API – jsou zobrazené na **zprávy** kartě.

 Chcete-li zobrazit zprávy, musí být projektu Unity [ladění projektu v přehrávač Unity](#debugging-your-project-in-a-unity-player) pro podporu ladění skriptů a pro import Visual Studio Tools for Unity balíček, který je nejvhodnější pro vaši verzi sady Visual Studio, a Visual Studio musí být [připojení Visual Studio Unity](#connecting-visual-studio-to-unity).

 Pokud chcete zobrazit chyby, upozornění a zprávy z Unity v sadě Visual Studio **seznam chyb** okno, můžete je zakázat v nabídce konfigurace.

### <a name="keyboard-shortcuts"></a>Klávesové zkratky
 Unity nástrojů pro Visual Studio funkci rychle přistupujete pomocí jejich klávesových zkratek. Zde je souhrn klávesových zkratek, které jsou k dispozici.

|Příkaz|Zástupce|Název příkazu zástupce|
|-------------|--------------|---------------------------|
|Otevřete Průvodce MonoBehavior|**Ctrl + Shift + M**|**EditorContextMenus.CodeWindow.ImplementMonoBehaviours**|
|Otevřete Průvodce rychlé MonoBehavior|**Ctrl+Shift+Q**|**EditorContextMenus.CodeWindow.QuickMonoBehaviours**|
|Otevřete Průzkumníka projektu Unity|**Alt + Shift + E**|**View.UnityProjectExplorer**|
|Přístup k dokumentaci Unity|**Ctrl + Alt + M, Ctrl + H**|**Help.UnityAPIReference**|
|Připojit k ladicí program Unity (player nebo editoru)|***žádná výchozí hodnota***|**Debug.AttachUnityDebugger**|

 Kombinace klávesových zkratek můžete změnit, pokud chcete výchozí nastavení. Informace o tom, jak ho změnit najdete v tématu [identifikuje a přizpůsobení klávesových zkratek v sadě Visual Studio](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).

## <a name="unity-debugging"></a>Ladění Unity
 Visual Studio Tools for Unity umožňuje ladění editoru a herní skripty pro svůj projekt Unity pomocí výkonné ladicího programu sady Visual Studio.

###  <a name="connecting-visual-studio-to-unity"></a> Připojování k Unity sady Visual Studio
 Visual Studio Tools for Unity Unity komunikuje přes UDP připojení. To znamená, zda se můžete připojit k instanci Unity spuštěn místně nebo kdekoli v síti stejným způsobem. Můžete připojit k žádné instance Unity můžete zobrazit v síti pomocí **vyberte instanci Unity** dialogové okno.

##### <a name="to-open-the-select-unity-instance-dialog"></a>Tím otevřete dialogové okno Vybrat instanci Unity

-   V sadě Visual Studio v hlavní nabídce zvolte **ladění**, **připojit ladicí program Unity**.

     ![Připojte ladicí program Unity. ] (../cross-platform/media/vstu_debugging_attach_unity_debugger.png "vstu_debugging_attach_unity_debugger")

-   *Nebo*, v sadě Visual Studio na stavovém řádku, zvolte ikonu moduly v pravém dolním rohu Visual Studio.

     ![Tato ikona znázorňuje, že VSTU je připojen k Unity. ] (../cross-platform/media/vstu_connection_connected.png "vstu_connection_connected")

> [!TIP]
>  Pokud ikonu moduly zobrazuje zaškrtnout, jste již připojeni k instanci Unity.

 **Vyberte instanci Unity** dialogové okno zobrazí některé informace o jednotlivých Unity instanci, která se můžete připojit k.

 ![Zvolte instanci Unity pro připojení k. ] (../cross-platform/media/vstu_connection_to_unity.png "vstu_connection_to_unity")

 **Projekt** název Unity projekt, který běží v této instanci aplikace Unity.

 **Počítač** název počítače nebo zařízení, která tuto instanci Unity běží na.

 **Typ** **Editor** Pokud tuto instanci Unity běží v rámci programu Editor Unity; **Player** Pokud je tato instance Unity samostatné přehrávač.

 **Port** číslo portu soketu UDP, která tuto instanci Unity je komunikaci přes.

> [!IMPORTANT]
>  Protože Visual Studio Tools for Unity a Unity instance komunikují přes síť soket UDP, brána firewall může požádat o něm. V takovém případě budete muset autorizovat připojení, aby mohl komunikovat VSTU a Unity.

### <a name="troubleshooting-the-connection-between-unity-and-visual-studio"></a>Řešení potíží s připojení mezi Unity a Visual Studio

#### <a name="confirm-editor-attaching-is-enabled"></a>Potvrďte, že Editor připojení je povoleno

V nabídce Unity vyberte **Upravit > Předvolby** a pak vyberte **externích nástrojů** kartě. Potvrďte, že **Editor připojení** zaškrtávací políčko je aktivní. Další informace naleznete [Unity předvolby dokumentaci](https://docs.unity3d.com/Manual/Preferences.html).

###  <a name="debugging-your-project-in-a-unity-player"></a> Ladění projektu v přehrávač Unity
 Visual Studio Tools for Unity můžete připojit přímo do aplikace Unity spuštěním v samostatné player, když nejsou spuštěné Unity Editor nebo pro ladění problémů, které jsou specifických pro platformu.

##### <a name="to-enable-script-debugging-in-a-unity-player"></a>Chcete-li povolit ladění skriptů v přehrávač Unity

-   Ujistěte se, že vytváříte vývoj sestavení s povoleným laděním skriptu. V nastavení sestavení projektu Unity, označte **vývoj sestavení** a **ladění skriptů** zaškrtávací políčka.

 ![Nakonfigurujte nastavení Unity sestavení pro ladění. ] (../cross-platform/media/vstu_debugging_build_settings.png "vstu_debugging_build_settings")

 Navíc k ladění aplikace Unity spuštěné v **Unity Web Player**, budete také muset nakonfigurovat ho na použití **vývoj verze kanál**.

##### <a name="to-configure-the-development-release-channel-in-unity-web-player"></a>Můžete nastavit kanál verze vývoj Unity Web Player

-   Web Player Unity v místní nabídce vyberte **verze kanál** a ujistěte se, že **vývoj** možnost je povolená.

    > [!IMPORTANT]
    >  Unity 4.2 a novější **verze kanál** položky kontextové nabídky je k dispozici v místní nabídce webové Player pouze při **Alt** není stisknuta klávesa, protože je otevřen v místní nabídce. Pokud Web Player běží na systému Mac OS X, stiskněte **možnost** klíče místo.

 Nakonec se ujistěte, že jste připojení k instanci Unity, která chcete ladit. Informace o tom, jak to udělat, najdete v článku [připojení Visual Studio Unity](#connecting-visual-studio-to-unity) části.

### <a name="debugging-a-dll-in-your-unity-project"></a>Ladění knihoven DLL ve vašem projektu Unity
 Celá řada vývojářů Unity jsou psaní kódu komponent jako externí knihovny DLL tak, aby funkce, které vyvíjejí můžete snadno sdílet s jinými projekty. Visual Studio Tools for Unity usnadňuje ladění kódu v těchto knihoven DLL bezproblémově se jiný kód ve vašem projektu Unity.

> [!NOTE]
>  V tomto okamžiku Visual Studio Tools for Unity podporuje pouze spravované knihovny DLL. Nepodporuje ladění nativního kódu knihovny DLL, jako jsou napsané v jazyce C++.

 Všimněte si, že podle scénáře popsaného v tomto poli předpokládá, že máte ve zdrojovém kódu – to znamená, vývoji nebo opakované použití kódu první strany nebo máte zdrojový kód do knihovny třetích stran a plánujete nasadit ve vašem Unity projektu jako knihovny DLL. Tento scénář nepopisuje ladění knihovny DLL, pro které nemáte zdrojového kódu.

##### <a name="to-debug-a-managed-dll-project-used-in-your-unity-project"></a>Ladění spravovaného projektu knihovny DLL použít ve vašem projektu Unity

1.  Přidáte existující projekt knihovny DLL do řešení sady Visual Studio generované Visual Studio Tools for Unity. Ne tak často může počáteční nové spravované projektu knihovny DLL tak, aby obsahovala komponent kódu v projektu Unity; Pokud je to tento případ, přidáte nový spravovaný projekt knihovny DLL do řešení sady Visual Studio místo. Další informace o přidání nového nebo existujícího projektu na řešení, najdete v tématu [postupy: Přidání projektů do řešení](https://msdn.microsoft.com/en-us/library/vstudio/ff460187.aspx).

     ![Do řešení přidáte do existujícího projektu knihovny DLL. ] (../cross-platform/media/vstu_debugging_dll_add_existing.png "vstu_debugging_dll_add_existing")

     V obou případech Visual Studio Tools for Unity udržuje odkaz na projekt, i když má soubory projektu a řešení vygenerovat znovu, takže potřebujete jednou proveďte tyto kroky.

2.  Odkaz správného profilu framework Unity v projektu knihovny DLL. V sadě Visual Studio, nastavte v dialogovém okně Vlastnosti projektu knihovny DLL **cílové rozhraní** vlastnost verzi Unity framework, který používáte. Toto je Unity základní knihovny tříd odpovídající kompatibility rozhraní API, že vaše cíle projektu, například úplné Unity, micro nebo webové základní knihovny tříd. To brání tomu, aby vaše knihovna DLL volání metod framework, které existují v jiných rozhraní nebo úrovně kompatibility, ale který nemusí existovat v Unity verzi, kterou používáte.

     ![Nastavte knihovnu DLL cílové rozhraní Unity framework. ] (../cross-platform/media/vstu_debugging_dll_target_framework.png "vstu_debugging_dll_target_framework")

3.  Zkopírujte knihovnu DLL do projektu Unity Asset složky. Prostředky v Unity, jsou soubory, které jsou zabaleny a nasazeny společně s aplikace Unity tak, že je lze načíst za běhu. Vzhledem k tomu, že v době běhu jsou propojené knihovny DLL, knihovny DLL musí být nasazený jako prostředky. Editoru Unity nasazované jako prostředek, vyžaduje knihovny DLL k uvedení v této složce prostředky ve vašem projektu Unity. Můžete to provést dvěma způsoby:

    -   Upravit nastavení sestavení projektu knihovny DLL zahrnout po integrovaný úlohu, která zkopíruje z jeho výstupní složky pro výstupní knihovnu DLL a PDB soubory **prostředky** složce projektu Unity.

    -   Změnit nastavení sestavení projektu knihovny DLL a nastavit jeho výstupní složky, jako **prostředky** složce projektu Unity. Soubory knihoven DLL a PDB bude uložena v umístění **prostředky** složky.

     Soubory PDB jsou potřebné pro ladění, protože obsahovat symboly pro ladění knihovnu DLL a mapování kód knihovny DLL na jeho podobě zdrojového kódu. Visual Studio Tools for Unity bude používat informace z knihovny DLL a PDB k vytvoření knihovny DLL. MDB souboru, který je formátem symbol ladění používá skriptovací stroj Unity.

4.  Ladění kódu. Teď můžete ladit kód zdroje knihovny DLL společně s projektu Unity zdrojový kód a použít všechny funkce, které se používají, jako je například zarážky ladění a procházení kódu.
