---
title: "Hledání a používání rozšíření Visual Studia | Microsoft Docs"
ms.custom: 
ms.date: 06/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.ExtensionManager
helpviewer_keywords:
- install extensions
- install packages
- managing extensions visual studio
ms.assetid: 4ca92d93-31b9-47ef-8109-4a429d9e2ca3
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0327ccaa52f3bd348246eea39b754f5c9069f3a1
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="finding-and-using-visual-studio-extensions"></a>Hledání a používání rozšíření Visual Studia
Rozšíření pro Visual Studio jsou kód balíčky, které běží v prostředí Visual Studio a poskytují nových nebo vylepšených funkcích nástroje Visual Studio. Můžete najít další informace o rozšíření Visual Studia zde: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  

 Můžete použít **rozšíření a aktualizace** dialogové okno instalace rozšíření sady Visual Studio a ukázky z webů a jiných umístění a potom povolit, zakázat, aktualizovat, nebo je odinstalovat. (**Nástroje nebo rozšíření a aktualizace**, nebo typ **rozšíření** v **Snadné spuštění** okno). Dialogové okno také ukazuje aktualizace nainstalované ukázky a rozšíření. Můžete také stáhnout rozšíření z webů nebo je můžete získat z jiných vývojáři.  

> [!NOTE]
>  Spouštění v sadě Visual Studio 2015, rozšíření hostované na Visual Studio Marketplace se automaticky aktualizuje.  Pomocí tohoto nastavení můžete změnit **rozšíření a aktualizace** dialogové okno.  Projděte část o **automatické aktualizace rozšíření** níže podrobnosti.  

## <a name="finding-visual-studio-extensions"></a>Hledání rozšíření Visual Studia  
 Můžete nainstalovat rozšíření z [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs). Rozšíření mohou být ovládací prvky, ukázky, šablony, nástroje nebo jiné součásti, které přidávají funkcionalitu do aplikace Visual Studio. Visual Studio podporuje rozšíření ve formátu balíčku VSIX – tyto zahrnují šablony projektů, šablon, položek **sada nástrojů** položek, součásti spravované rozšíření Framework (MEF) a VSPackages. Můžete také stáhnout a nainstalovat na základě MSI rozšíření, ale **rozšíření a aktualizace** nemůže povolit ani zakázat je dialogové okno. Visual Studio Marketplace obsahuje rozšíření VSIX a souboru MSI.  

## <a name="installing-or-uninstalling-visual-studio-extensions"></a>Instalace nebo odinstalace rozšíření Visual Studia  
 V **rozšíření a aktualizace**, najít rozšíření, kterou chcete nainstalovat. (Pokud znáte název nebo část názvu rozšíření, můžete hledat v **vyhledávání** okno.) Klikněte na tlačítko **Stáhnout**.  Rozšíření se naplánuje pro instalaci. Rozšíření se nainstaluje, když jsou uzavřeny všechny instance sady Visual Studio.

 Pokud se pokusíte nainstalovat rozšíření, která obsahuje závislosti, instalační služba zkontroluje, zda jsou již tyto závislosti nainstalovány. Pokud nejsou nainstalovány, **rozšíření a aktualizace** dialogové okno uvádí závislosti, které je třeba nainstalovat před instalací rozšíření.  

 Pokud chcete přestat používat rozšíření, lze jej zakázat nebo odinstalovat. Zakázáním rozšíření zůstane rozšíření nainstalováno, ale nedojde k jeho načtení. Můžete zakázat pouze VSIX rozšíření; rozšíření, které jsou nainstalované s použitím souboru MSI lze pouze odinstalovat. Najít rozšíření a klikněte na tlačítko **odinstalace** nebo **zakázat**. Chcete-li uvolnit zakázané rozšíření, musíte restartovat Visual Studio.  

## <a name="per-user-and-administrative-extensions"></a>Rozšíření pro jednotlivé uživatele a administrativní rozšíření  
 Většina rozšíření jsou rozšíření na uživatele a jsou nainstalovány ve **%LocalAppData%\Microsoft\VisualStudio\\< verze sady Visual Studio\>\Extensions\\**  složky. Několik rozšíření jsou pro správu rozšíření a jsou nainstalovány ve  **\<instalační složka nástroje Visual Studio > \Common7\IDE\Extensions\\**  složky.  

 Abychom mohli chránit váš systém proti rozšíření, která může obsahovat chyby nebo škodlivý kód, můžete omezit uživatelská rozšíření načíst jenom v případě, že spuštění sady Visual Studio s normální uživatelské oprávnění. To znamená, že uživatelská rozšíření zakázáno při spuštění sady Visual Studio s oprávněními správce. Chcete-li to provést, přejděte na **rozšíření a aktualizace** stránka Možnosti (**Nástroje / možnosti**, **prostředí**, **rozšíření a aktualizace**, nebo jenom typ **rozšíření** v **Snadné spuštění** okno). Vymazat **zatížení na rozšíření uživatele při spuštění jako správce** zaškrtněte políčko a potom restartujte Visual Studio.  

## <a name="automatic-extension-updates"></a>Aktualizace automatické rozšíření  
 Rozšíření na uživatele se automaticky aktualizují, pokud je k dispozici pro Visual Studio Marketplace nové verze.  Rozpoznán a nainstalován na pozadí a v dalším restartování sady Visual Studio novou verzi rozšíření, budou používat novou verzi rozšíření.  

 Pouze na uživatele rozšíření lze aktualizovat automaticky.  Správce rozšíření, které jsou nainstalovány pro všechny uživatele se nebude aktualizovat a ručně nainstalujte nové verze prostřednictvím **rozšíření a aktualizace** dialogovém okně **aktualizace** uzlu. Uvidíte, které přípony bude automaticky aktualizován v podokně Podrobnosti rozšíření **rozšíření a aktualizace** dialogové okno.  

 Pokud chcete vypnout automatické aktualizace, můžete zakázat funkci pro všechna rozšíření a pouze konkrétní rozšíření.  

-   Chcete-li zakázat automatické aktualizace pro všechna rozšíření, zvolte **rozšíření a aktualizace nastavení změnit** odkaz v **rozšíření a aktualizace** dialogové okno a zrušte zaškrtnutí políčka **automaticky aktualizovat rozšíření**.  

-   Zakázat automatické aktualizace pro konkrétní příponu, zrušte zaškrtnutí políčka **automaticky aktualizovat toto rozšíření** možnosti v podokně podrobností rozšíření na pravé straně **rozšíření a aktualizace** dialogové okno.  

> [!NOTE]
>  Od verze Visual Studio 2015 Update 2, můžete zadat (v **Nástroje / možnosti / prostředí nebo rozšíření a aktualizace**) tom, zda má funkce Automatické aktualizace pro rozšíření na uživatele, všechna rozšíření uživatele nebo oba (výchozí nastavení).  

## <a name="extension-crash-notifications"></a>Rozšíření havárií oznámení

V aplikaci Visual Studio 2017 (verze 15.3 - Preview) Visual Studio vás upozorní, pokud má podezření, že rozšíření byl součástí havárie v předchozí relaci. Když Visual Studio dojde k chybě, ukládá zásobník výjimek. Při příštím spuštění Visual Studio zkontroluje zásobníku, počínaje listu a směřování ve znalostní bázi. Pokud Visual Studio zjistí, že rámeček patří do modul, který je součástí nainstalované a povolené rozšíření, upozorní vás zprávou, jako

  "Předchozí relace byla neočekávaně ukončena. Zakázání rozšíření 'extension_name' mohou pomoci zabránit podobné problémy."

Můžete ignorovat oznámení nebo provést jednu z následujících akcí:

-   Zvolte **zakáže toto rozšíření**. Visual Studio zakáže rozšíření a umožňuje vědět, jestli je potřeba restartovat systém pro zakázání vstoupily v platnost. Můžete je znovu povolit rozšíření v **rozšíření a aktualizace** dialogové, pokud chcete.

-   Zvolte **nezobrazovat pro tuto příponu**. Prostředí IDE již nebude zobrazovat oznámení o dojde k chybě související s touto příponou, ale zobrazí oznámení pro ostatní rozšíření přidružená dojde k chybě.

-   Zvolte **Další** zobrazíte toto téma nápovědy ve výchozím prohlížeči.

-   Vyberte **X** tlačítko na konci oznámení zavření oznámení. Pokud stejné rozšiřující se zabývá havárie v relaci budoucí, znovu se zobrazí oznámení.

> [!NOTE]
>  Oznámení havárií znamená, že byla pouze než rozšíření modulů v zásobníku při chybě. Je však nemusí znamenat, že rozšíření samotné způsobila havárii. Je možné, že rozšíření volat kód, který je součástí sady Visual Studio a tento kód způsobila havárii. Však oznámení může být stále užitečné, pokud scénář, která vedla k havárii není pro vás důležité. V takovém případě zakázání rozšíření zabraňuje stejné havárie v budoucnu bez dopadu na produktivitu.


## <a name="sample-master-copies-and-working-copies"></a>Ukázka hlavní kopie a práci kopie  
 Při instalaci online ukázky je řešení uloženo na dvou místech:  

-   Pracovní kopie je uložen v umístění, které jste zadali v **nový projekt** dialogové okno.  

-   Samostatná hlavní kopie je uložena v počítači.  

 Můžete použít **rozšíření a aktualizace** dialogové okno k provedení těchto úloh souvisejících s ukázky:  

-   Zobrazit seznam hlavních kopií ukázek, které jste nainstalovali.  

-   Zakázat nebo odinstalovat hlavní kopii ukázky.  

-   Instalovat balíky ukázek, což jsou kolekce ukázek, které se týkají technologie nebo funkce.  

-   Nainstalujte jednotlivé online ukázky. (Můžete to provést taky **nový projekt** dialogové okno.)  

-   Zobrazit upozornění na aktualizace při zveřejnění změny zdrojového kódu nainstalovaných ukázek.  

-   Aktualizujte hlavní kopii nainstalované ukázka po oznámení o aktualizaci.  

## <a name="installing-without-using-the-extensions-and-updates-dialog-box"></a>Instalace bez použití rozšíření a dialogového okna Aktualizace  
 Rozšíření, která byla součástí VSIX soubory mohou být k dispozici v umístění než Visual Studio Marketplace. **Rozšíření a aktualizace** dialogové okno se nepodařilo zjistit tyto soubory však můžete nainstalovat soubor VSIX dvojitým kliknutím na soubor nebo soubor výběrem a stisknutím klávesy ENTER. Potom postupujte podle pokynů. Pokud je nainstalovaná rozšíření, můžete použít **rozšíření a aktualizace** dialogové okno povolit, zakázat nebo ho odinstalovat.  

## <a name="extension-types-not-supported-by-the-extensions-and-updates-dialog-box"></a>Typy rozšíření nepodporuje rozšíření a aktualizace dialogové okno  
 Visual Studio bude dál podporovat rozšíření, které jsou nainstalované ve Microsoft Installer (MSI) ale není pomocí **rozšíření a aktualizace** dialogové okno bez úprav.  

> [!TIP]
>  Pokud na základě MSI rozšíření obsahuje souboru extension.vsixmanifest, rozšíření se objeví v **rozšíření a aktualizace** dialogové okno.
