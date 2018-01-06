---
title: Essentials UX pro sadu Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a793cf7a-f230-43ce-88d0-fa5d6f1aa9c7
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f9d04da421b3b59609269b4f91a487d22adc80e3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ux-essentials-for-visual-studio"></a>Essentials UX pro sadu Visual Studio
## <a name="best-practices"></a>Doporučené postupy  
  
### <a name="1-be-consistent-within-the-visual-studio-environment"></a>1. Být konzistentní v rámci prostředí Visual Studio.  
  
-   Postupujte podle existující [interakce vzory](interaction-patterns-for-visual-studio.md) v rámci prostředí.  
  
-   Funkce, které mají být v souladu s jazykem visual prostředí návrhu a [řemeslné ruční práce požadavky](evaluation-tools-for-visual-studio.md).  
  
-   Používejte sdílené příkazy a řídí, pokud existují.  
  
-   Pochopení hierarchii nástroje Visual Studio a jak vytváří kontextu a disky uživatelského rozhraní.  
  
### <a name="2-use-the-environment-service-for-fonts-and-colors"></a>2. Použijte službu prostředí pro písma a barev.  
  
-   Uživatelské rozhraní by měly dodržovat aktuální [prostředí písma](fonts-and-formatting-for-visual-studio.md) nastavení, pokud je vystaven pro vlastní nastavení na stránce písma a barev v dialogovém okně Možnosti.  
  
-   Prvky uživatelského rozhraní musí používat [VSColor služby](colors-and-styling-for-visual-studio.md), používání sdíleného tokeny prostředí nebo konkrétních funkcí tokeny.  
  
### <a name="3-make-all-imagery-consistent-with-the-new-vs-style"></a>3. Zkontrolujte všechny obrazů konzistentní s nový styl VS.  
  
-   Postupujte podle zásady designu sady Visual Studio ikony, glyfů a jiné grafiky.  
  
-   Neumísťujte text v grafické elementy.  
  
### <a name="4-design-from-a-user-centric-perspective"></a>4. Návrh z hlediska zaměřenou na uživatele.  
  
-   Vytvořte tok úkolů před jednotlivých funkcí v něm.  
  
-   Se seznamte s uživateli a ujistěte se, že znalosti explicitní ve vašem specifikace.  
  
-   Při revizi uživatelského rozhraní, vyhodnoťte dokončení prostředí a také podrobnosti.  
  
-   Návrh vašeho uživatelského rozhraní, aby zůstala funkčnosti a atraktivní bez ohledu na to, národní prostředí a jazyka.  
  
## <a name="screen-resolution"></a>Rozlišení obrazovky  
  
### <a name="minimum-resolution"></a>Minimální rozlišení  
 - Minimální rozlišení pro Visual Studio Dev14 je **1280 × 720**. To znamená, že je *možné* použití sady Visual Studio na toto řešení, i když nemusí být optimální uživatelské prostředí. Není zaručeno, že všechny aspekty bude možné použít rozlišení nižší než 1280 × 720.  
  
 - Cíl řešení pro sadu Visual Studio je **1366 x 768**. Toto je nejnižší řešení, kdy jsme promise *dobrý* činnost koncového uživatele.

 - Výška počáteční dialogu by měl být **menší než 700 pixelů**, takže se vejde do minimální rozlišení rámce IDE při 96 dpi.
  
### <a name="high-density-displays"></a>V podobě výkonných zobrazí  
 Uživatelského rozhraní v sadě Visual Studio musí fungovat i v všechny DPI škálování faktorů, které Windows podporuje mimo pole: 150 %, 200 % a 250 %.  
  
## <a name="anti-patterns"></a>Proti vzory  
 Visual Studio obsahuje mnoho příklady uživatelského rozhraní, které následují Naše pokyny a osvědčené postupy. Ve snaze zajistit konzistentní vývojáři často půjčit z podobná co jste vytváření vzory návrhu uživatelského rozhraní produktu. I když toto je dobré přístup, pomůže nám jednotka konzistence v interakci s uživatelem a vizuální návrh, v některých případech dodávané funkce s několika podrobnosti, které splňují Naše pokyny z důvodu omezení plán nebo nedostatky stanovení priorit. V těchto případech jsme nechcete, aby týmy zkopírovat jeden z těchto "proti vzorků" vzhledem k tomu, že udrželi chybné nebo nekonzistentní uživatelského rozhraní v prostředí Visual Studio.  
  
### <a name="required-fieldssettings-shown-in-error-state-by-default"></a>Požadované pole nebo nastavení zobrazené v chybovém stavu, ve výchozím nastavení  
  
#### <a name="feature-team-goals"></a>Funkce týmové cíle  
  
-   Upozorněte uživatele, že jejich přidali element, který musí být nakonfigurovaná.  
  
-   Upozornit uživatele na oblasti, které je třeba vstup.  
  
#### <a name="anti-pattern-solution"></a>Proti vzor řešení  
 Jakmile uživatel inicioval akce a předtím, než se dokončí úlohu, umístěte okamžitě kritické zastavení ikony vedle oblasti, které vyžadují konfiguraci.  
  
#### <a name="example-manifest-designer-declarations"></a>Příklad: Deklarace návrháře manifestu  
 Přidání deklaraci do seznamu okamžitě umístí v chybovém stavu, která zůstává v platnosti do uživatel nastaví požadované vlastnosti.  
  
 V takovém případě je další problém protože obsahuje ikonu, která používá pro výstrahy "&times;" ikonu, takže ikonu běžné odebrat nelze použít u ní. V důsledku toho uživatelského rozhraní pomocí tlačítka odebrat, více clunky ovládacího prvku.  
  
 ![Umístění uživatelského rozhraní v chybovém stavu, ve výchozím nastavení je vzor proti Visual Studio. ] (../../extensibility/ux-guidelines/media/manifestdesignererrordeclarationsanti-pattern.png "ManifestDesignererrordeclarationsanti – vzor")<br />Umístění uživatelského rozhraní v chybovém stavu, ve výchozím nastavení je vzor proti Visual Studio.
  
#### <a name="alternatives"></a>Alternativy  
 Může být mnohem lepší řešení tohoto problému:  
  
-   Povolí uživateli přidat deklaraci bez upozornění a poté přesuňte okamžitě pro nastavení vlastností položky.  
  
-   Přidat na ikonu upozornění (gold trojúhelník) když se aktivuje z položky, jako třeba chcete přidat jiný deklaraci do seznamu nebo pokusí změnit karty v návrháři.  
  
-   Pokud se uživatel pokusí změnit karty před nastavením vlastnosti na všechny deklarace, pop dialog s vysvětlením, že aplikace nebude sestavení (nebo libovolnou důsledky) dokud nebudou vyřešeny upozornění. Pokud uživatel zavře dialogové okno a změní karty přesto pak ikonu (kritický nebo upozornění v případě potřeby) je přidat na kartu deklarace.  
  
### <a name="multiple-clicks-to-dismiss-ui"></a>Více klikne na tlačítko pro zavření uživatelského rozhraní  
  
#### <a name="feature-team-goals"></a>Funkce týmové cíle  
 Nepovolit uživatelům bez první vidět text vysvětlení zavření uživatelského rozhraní.  
  
#### <a name="anti-pattern"></a>Proti vzor  
 Tým vkládání video odkazy do různých místech v rámci rozhraní VS rozhodli proti běžný vzor "&times;" Zavřít tlačítko a popisu tlačítka vysvětlení jako určeného UX a místo toho implementována rozevíracího seznamu a "Nezobrazovat" propojení.  

#### <a name="example-video-links-in-team-explorer"></a>Příklad: video odkazy v Team Explorer
Chcete-li přinutit uživatele ke čtení vysvětlující text před zavření uživatelského rozhraní je proti vzor v sadě Visual Studio. Odkazy správně navrženou, videa by měl zobrazí popisek s dalšími informacemi na hover a kliknutím na "&times;" by měl zavřete zprávu, bez nutnosti další interakce.


 ![Vysvětlující text anti & č. 45; vzor & č. 45; nesprávný](../../extensibility/ux-guidelines/media/incorrectuseofmultipleclicks.png "Incorrectuseofmultipleclicks")<br />Vzor nesprávné video propojení
  
#### <a name="result"></a>Výsledek  
 Místo jednoduché tlačítko Zavřít (jedním kliknutím) a uživatel bude muset používat dvě klikne na tlačítko se jednoduše zavřít uživatelského rozhraní v každé místo, které zobrazí video odkazy.  
  
#### <a name="alternatives"></a>Alternativy  
 Správné návrhu v tomto případě bude postupovat podle vzoru běžné aplikace Internet Explorer, Office a Visual Studio: při přechodu myší, uživatel uvidí popis popisek a jedním kliknutím skryje uživatelské rozhraní.  
  
 ![Vysvětlující text anti & č. 45; vzor & č. 45; správné](../../extensibility/ux-guidelines/media/explanatorytextanti-pattern-correct.png "opravte vzor Explanatorytextanti")<br />Vzor správné video odkaz
  
### <a name="using-command-bars-for-settings"></a>Použití pro nastavení panely příkazů  
 **Obrázek A** představuje tento vzor proti: vložení nastavení pod příkazového tlačítka, které se vztahují k více než jen příkazu. V této nákresu jsou příkazy kromě spustit ladění – jako zobrazení v prohlížeči, spustit bez ladění a Krokovat s vnořením –, bude respektovat nastavení vybrané.  

  ![Obrázek A: příkaz panelu proti vzor](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurea.png "Commandbaranti. vzor FigureA")<br />Obrázek A: příkazového řádku proti vzor
  
 Mírně lepší, ale stále nežádoucí, je nastavení tohoto typu uvedení v panelech nástrojů, jak je znázorněno v **obrázek B**. Při tlačítka rozdělení trvat méně místa a jsou proto zlepšení přes rozevírací seznamy, i návrhy stále používají panelu nástrojů na podporu něco, co není skutečně příkaz.  
 
 ![Obrázek B: lépe, ale stále proti vzor příkazového řádku](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figureb.png "Commandbaranti. vzor FigureB")<br />Obrázek B: lepší, ale stále proti vzor příkazového řádku
 
  V správné přístupu ukazuje **obrázek C**, nastavení je vázaný na řadu příkazů. Neexistuje žádné globální nastavení se nastavuje a jsme se právě přepínání mezi čtyři příkazy. Toto je pouze situace, ve kterém jsou přijatelné příkazy na panelu nástrojů. 

 ![Obrázek C: Opravte použití sady Visual Studio příkazového řádku vzor](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurec.png "Commandbaranti. vzor FigureC")<br />Obrázek C: správné použití sady Visual Studio příkazového řádku vzor
   
### <a name="control-anti-patterns"></a>Vzory ovládacích prvků proti  
 Některé proti vzorky se jednoduše nesprávné použití nebo prezentace ovládací prvek nebo skupiny ovládacích prvků.  
  
#### <a name="underlining-used-as-a-group-label-not-a-hyperlink"></a>Podtržení použitý jako název skupiny, není hypertextový odkaz  
 Podtržení text by měl použít pouze pro hypertextové odkazy.  
  
 **Špatné:**    
 ![Podtržený text, který není hypertextový odkaz je vzor proti Visual Studio. ] (../../extensibility/ux-guidelines/media/0102-g_grouplabelincorrect.png "0102 g_GroupLabelIncorrect")<br />Podtržený text, který není hypertextový odkaz je vzor proti Visual Studio.
  
 **Dobré:**   
 ![Ve správně, text hypertextového odkazu se zobrazí prostým v prostředí písmo. ] (../../extensibility/ux-guidelines/media/0102-h_grouplabelcorrect.png "0102 h_GroupLabelCorrect")<br />Ve správně, text hypertextového odkazu se zobrazí prostým v prostředí písmo.
  
#### <a name="clicking-on-a-check-box-results-in-a-pop-up-dialog"></a>Kliknutím na políčko výsledky v automaticky otevíraná okna  
 Kliknutím na políčko "Povolit vzdálená plocha pro všechny role" v průvodci "Publikování aplikace systému Windows Azure" okamžitě zobrazí automaticky otevírané okno dialogové okno, proti vzor Visual Studio. Kromě toho zaškrtněte políčko pole nevyplní zaškrtávací políčko po vybrat, jiné proti vzor interakce.  
  
 ![Dialogové okno převedou po kliknutí na zaškrtávací políčko je vzor proti Visual Studio. ] (../../extensibility/ux-guidelines/media/0102-i_checkboxpopup.png "0102 i_CheckboxPopup")<br />Dialogové okno převedou po kliknutí na zaškrtávací políčko je vzor proti Visual Studio.
  
### <a name="hyperlink-anti-patterns"></a>Vzory proti hypertextový odkaz  
 Následující příklad obsahuje dva proti vzory.  
  
1.  Popředí vypnutí při přechodu červenou znamená nepoužívá správná barva sdílené ze služby písma.  
  
2.  "Další informace" není vhodné text pro odkaz na toto téma. Cílem uživatele se dozvědět víc, že je pochopit následky, které si sami vyberou.  
  
 ![Ignoruje službu barva a pomocí "Další informace" pro hypertextové odkazy jsou proti vzory Visual Studio. ] (../../extensibility/ux-guidelines/media/0102-j_hyperlinkincorrect.png "0102 j_HyperlinkIncorrect")<br />Ignoruje službu barva a pomocí "Další informace" pro hypertextové odkazy jsou proti vzory Visual Studio.  
  
 **Lepší řešení:** představovat otázku, uživatel by s dotazem, kliknutím na odkaz.  
  
-   Jak fungují služby Windows Azure?  
  
-   Pokud mají projektu Windows Azure Mobile Services?  
  
#### <a name="using-click-here-for-links"></a>Použití "Kliknutím sem" pro odkazy  
 Hypertextové odkazy by měl být self-descriptive. Je proti vzor používat "Kliknutím sem" nebo všechny podobné variace.  
  
 **Chybný:** "Kliknutím sem pokyny o tom, jak vytvořit nový projekt."
  
 **Dobré:** "Vytvoření nového projektu?"