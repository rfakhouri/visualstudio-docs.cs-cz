---
title: "Možnosti, textový Editor, C/C++, Upřesnit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C\C++.Advanced
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Advanced
- VS.ToolsOptionsPages.Text_Editor.C/C++.Advanced
helpviewer_keywords: Text Editor Options dialog box, advanced
ms.assetid: 67c82ae5-fddd-49df-baec-8e7498b156f3
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6870313900da464bb2e8a9ae7facfea8c87b72d4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="options-text-editor-cc-advanced"></a>Možnosti, textový editor, C/C++, upřesnit
Změníte-li tyto možnosti, můžete změnit chování související s IntelliSense a procházení databáze, když jste programování v C nebo C++.  
  
 Pro přístup k této stránce v **možnosti** dialogové okno, v levém podokně rozbalte **textového editoru**, rozbalte položku **C/C++**a potom zvolte **Upřesnit**.  
  
> [!NOTE]
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. V tématu [přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="browsingnavigation"></a>Procházení nebo navigace  
 Měli byste nikdy vybrat tyto možnosti s výjimkou v případě výjimečných řešení je tak velký, že aktivita databáze používá nepřijatelné množství systémové prostředky.  
  
 **Zakázat databáze**  
 Všechny použití kódu procházení databáze (SDF), všechny ostatní možnosti procházení nebo navigace a všechny funkce IntelliSense s výjimkou #include automaticky dokončení jsou zakázány.  
  
 **Zakázat aktualizace databáze**  
 Databáze se otevře, jen pro čtení a žádné aktualizace proběhne, jako jsou soubory upravovat. Většinu funkcí budou i nadále fungovat. Ale jako jsou provedeny úpravy, data se stane zastaralé a získáte nesprávné výsledky.  
  
 **Zakázat automatické aktualizace databáze**  
 Kód procházení databáze nebudou automaticky aktualizovány při změně zdrojových souborů. Ale pokud otevřete **Průzkumníku řešení**, otevřete místní nabídky projektu a zvolte **Prohledat znovu řešení**, budou kontrolovat všechny soubory zastaralé a zaktualizuje databázi.  
  
 **Zakázat implicitní soubory**  
 Kód procházení databáze není shromažďování dat pro soubory, které nebyly zadány v projektu. Projekt obsahuje zdrojové soubory a soubory hlaviček, které jsou explicitně určena. Implicitní soubory jsou zahrnuty explicitní soubory (například afxwin.h, odkazující na Windows a atlbase.h). Za normálních okolností systém vyhledá tyto soubory a také je indexy pro různé funkce procházení (včetně přejít na). Pokud zvolíte tuto možnost, tyto soubory nejsou indexovány a některé funkce nejsou k dispozici pro ně. Pokud zvolíte tuto možnost, jsou vybraná také implicitně "Zakázat implicitní čištění" a "Zakázat externí závislosti".  
  
 **Zakázat implicitní čištění**  
 Kód procházení databáze není vyčistit až implicitní soubory, které se už neodkazuje. Tato možnost zabrání implicitní soubory odebírán z databáze, pokud se už používá. Například, pokud přidáte `#include` direktivy, který odkazuje mapi.h na jednu z vaší zdrojové soubory, mapi.h bude nalezen a indexovat. Pokud pak odeberete #include a soubor neodkazuje jinde, informace o něm budou odebrány nakonec, pokud zvolíte tuto možnost. (Najdete v článku **Prohledat znovu Interval řešení** možnost.) Tato možnost je ignorována, pokud explicitně znovu prohledat řešení.  
  
 **Zakázat složky externí závislosti**  
 Složka vnější závislosti pro každý projekt, není vytvoří nebo aktualizuje. V **Průzkumníku**, každý projekt obsahuje vnější závislosti složky, která obsahuje všechny implicitní souborů pro tento projekt. Pokud zvolíte tuto možnost, že složka nezobrazí.  
  
 **Znovu vytvořte databáze**  
 Znovu vytvořte kód procházení databáze z nic příštím načte řešení. Pokud zvolíte tuto možnost, soubor databáze SDF se odstraní při dalším načtení řešení, což způsobuje databáze znovu vytvořit a indexované všechny soubory.  
  
 **Prohledat znovu Interval řešení**  
 Úloha 'Prohledat znovu řešení nyní' je naplánováno interval, který zadáte. Je nutné zadat rozmezí 0 až 5000 minut. Výchozí hodnota je 60 minut. Při řešení Probíhá prohledávání, časová razítka souboru se kontroluje k určení, zda soubor byl změněn mimo prostředí IDE. (Automaticky se sledují změny provedené v prostředí IDE, a soubory jsou aktualizovány.) Implicitně zahrnuté soubory jsou zkontrolována k určení, zda budou se všechny stále odkazuje.  
  
## <a name="diagnostic-logging"></a>Protokolování diagnostiky  
 Tyto možnosti jsou k dispozici v případě, že Microsoft požádá o shromažďování rozšířené informace o vyřešení problému. Informace o protokolování není vhodný pro uživatele, a doporučujeme nechat zakázané.  
  
 **Povolení protokolování**  
 Povolí protokolování diagnostiky v okně výstupu.  
  
 **Úroveň protokolování**  
 Nastavení protokolu podrobností, od 0 do 5.  
  
 **Protokolování filtru**  
 Filtry Zobrazí typů událostí pomocí bitová maska.  
  
 Nastavte pomocí součet kterékoli z následujících možností:  
  
-   0 – žádný  
  
-   1 - Obecné  
  
-   2 – nečinnosti  
  
-   4 – pracovní položky  
  
-   8 - IntelliSense  
  
-   16 – ACPerf  
  
-   32 - ClassView  
  
## <a name="fallback-location"></a>Záložní umístění  
 Záložní umístění je, kam jsou umístěny podpůrných souborů SDF a IntelliSense (například iPCH), pokud se nepoužívá primární umístění (adresář řešení). Tato situace může nastat, uživatel nemá oprávnění k zápisu do adresáře řešení nebo adresář řešení je v pomalé zařízení. Výchozí záložní umístění je v adresáři temp uživatele.  
  
 **Vždy používat záložní umístění**  
 Určuje, zda kód procházení databáze a soubory IntelliSense měli vždy uloženy ve složce, kterou zadáte jako "Záložní umístění", není vedle soubor .sln. Prostředí IDE se nikdy nepokouší pro soubory SDF nebo iPCH vedle adresář řešení a bude vždy používat záložní umístění.  
  
 **Bez varování-li použít záložní umístění**  
 Nejsou informován nebo dotaz, zda se používá záložní umístění. Za normálních okolností IDE vám oznámí, pokud se muselo používat záložní umístění. Tato možnost vypne tohoto upozornění.  
  
 **Záložní umístění**  
 Tato hodnota se používá jako sekundární umístění pro uložení kód procházení databáze nebo soubory IntelliSense. Ve výchozím nastavení je dočasný adresář záložní umístění. Prostředí IDE vytvoří podadresáře pod zadanou cestu (nebo k dočasnému adresáři), který obsahuje název řešení spolu s hodnotou hash úplnou cestu k řešení, což zabraňuje problémy s názvy řešení zůstává stejné.  
  
## <a name="intellisense"></a>IntelliSense  
 **Automatické rychlé informace**  
 Popisy tlačítek QuickInfo umožňuje při přesunutí ukazatele myši na text.  
  
 **Zakázat IntelliSense**  
 Zakáže všechny funkce IntelliSense. IDE nevytvoří VCPkgSrv.exe procesy pro žádosti o služby IntelliSense a žádné funkce IntelliSense, budou fungovat (QuickInfo, seznam členů, automatické dokončení Param Nápověda). Také je zakázána sémantického zabarvení a zvýrazňování odkazu. Tato možnost není zakázat procházení funkce, které spoléhají výhradně na databázi (včetně navigačním panelu, ClassView a vlastnost okno).  
  
 **Zakázat automatické aktualizace**  
 IntelliSense aktualizace je zpožděno. dokud se nevytvoří požadavek skutečné pro technologii IntelliSense. Toto zpoždění může mít za následek delší dobu provádění první operace IntelliSense v souboru, ale může být vhodné nastavit tuto možnost na velmi pomalé nebo omezené prostředků počítače. Pokud zvolíte tuto možnost, také implicitně vyberte možnosti "Zakázat Error Reporting" a "Zakázat podtržení vlnovkou".  
  
 **Zakázat zasílání zpráv o chybách**  
 Zakáže hlášení chyb IntelliSense prostřednictvím podtržení vlnovkou a v okně Seznam chyb. Zakáže také analýza pozadí, který je spojen s zasílání zpráv o chybách. Pokud zvolíte tuto možnost, také implicitně zvolte možnost "Zakázat podtržení vlnovkou".  
  
 **Zakázat podtržení vlnovkou**  
 Zakáže podtržení vlnovkou chyba IntelliSense. Red "podtržení vlnovkou" Nezobrazovat v okně editor, ale chyba se přesto objeví v okně Seznam chyb.  
  
 **Zakázat #include automatické dokončení**  
 Zakáže Automatické doplňování `#include` příkazy.  
  
 **Použít dál lomítko v #include automatické dokončení**  
 Aktivuje automatické doplňování `#include` příkazy při "/" se používá. Výchozí oddělovač, který je zpětné lomítko,\'. Kompilátor můžete buď přijmout, proto tuto možnost použijte, chcete-li určit, které používá vaše základu kódu.  
  
 **Maximální počet mezipaměti jednotky překladu**  
 Maximální počet překlad jednotky, které budou zachovány v jednom okamžiku active pro požadavky IntelliSense. Zadejte hodnotu v rozmezí 2 až 15. Toto číslo se vztahuje přímo k maximální počet VCPkgSrv.exe procesů, které budou spouštět (pro danou instanci sady Visual Studio). Výchozí hodnota je 2, ale pokud budete mít k dispozici paměť, můžete tuto hodnotu zvýšit a případně dosáhnout mírně lepší výkon v IntelliSense.  
  
 Další informace o jednotkách překlad najdete v tématu [fáze překladu](/cpp/preprocessor/phases-of-translation).  

 **Člen seznamu tečkou šipky**  
 Nahradí '.' s '->' v případě potřeby pro seznam členů.

 **Zakázat seznam agresivní členů**  
 Při zadávání názvu typu nebo proměnné se nezobrazí seznam členů. V seznamu se zobrazí až po zadání některé z potvrzení znaky, jak jsou definovány v **člen seznamu potvrzení znaků** možnost.  
  
 **Vypnout člen seznamu klíčová slova**  
 Klíčová slova jazyka jako `void`, `class`, `switch` nezobrazí v seznamu návrhy člen.  
  
 **Vypnout člen Vypsat fragmenty kódu**  
 Fragmenty kódu nezobrazí v seznamu návrhy člen.  
  
 **Zakázat sémantického zabarvení**  
 Vypne všechny zabarvení kódu s výjimkou klíčová slova jazyka, řetězce a komentáře.  
  
 **Potvrzení seznamu inteligentní člena**  
 Přidá řádek, když zvolíte klávesy Enter na konci plně typu aplikace word.  
  
 **Režim filtrování seznamu členů**  
 Nastaví typ odpovídající algoritmus. **Přibližné** vyhledá nejvíce možné odpovídá, protože používá algoritmus, který je podobný kontrola pravopisu k vyhledání shody, které jsou podobné, ale nejsou identické. **Inteligentní filtrování** odpovídá dílčích řetězců i v případě, že nejste na začátku slova. **Předpony** odpovídá jen na stejné dílčích řetězců, které začínají na začátku slova.  
  
 **Člen seznamu potvrzení znaků**  
 Určuje znaky, které způsobí aktuálně zvýrazněná návrhu seznam členů být zapsána. Můžete přidat nebo odebrat znaky z tohoto seznamu.  
  
## <a name="references"></a>Odkazy  
 **Zakázat řešení**  
 Z důvodů výkonu najít všechny odkazy zobrazí výsledky nezpracovaná textové vyhledávání ve výchozím nastavení místo použití technologie IntelliSense ověření kandidáti. Pro více přesné výsledky na všech najít operace můžete zaškrtnutí tohoto políčka zrušte. Chcete-li filtrovat na základě za vyhledávání, otevřete místní nabídku pro seznam výsledků a poté zvolte "Vyřešit výsledky."  
  
 **Skrýt nepotvrzeného**  
 Skryjte nepotvrzeného položky ve výsledcích najít všechny odkazy. Pokud jste se zrušit nastavení "Zakázat řešení" možnost, můžete tuto možnost Skrýt nepotvrzeného položek ve výsledcích.  
  
 **Zakázat, zvýrazňování odkazu**  

 ## <a name="text-editor"></a>Textový editor
 **Povolit rozbalení oborů**  
 Pokud je povoleno, je nutné uvést vybraný text s složené závorky, zadáním ' {' do textového editoru.  
  
 **Povolit rozbalení priorit**  
 Pokud je povoleno, je nutné uvést vybraný text v závorkách, zadáním ' (' do textového editoru.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení možností editoru pro konkrétní jazyk](../../ide/reference/setting-language-specific-editor-options.md)
