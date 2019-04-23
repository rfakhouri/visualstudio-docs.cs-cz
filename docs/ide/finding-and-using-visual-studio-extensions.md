---
title: Vyhledání a používání rozšíření
ms.date: 01/30/2019
ms.topic: conceptual
f1_keywords:
- vs.ExtensionManager
helpviewer_keywords:
- install extensions
- install packages
- managing extensions visual studio
ms.assetid: 4ca92d93-31b9-47ef-8109-4a429d9e2ca3
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3e282cdfda27579fd83871153a19897652d55865
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60113102"
---
# <a name="find-and-use-visual-studio-extensions"></a>Vyhledání a používání rozšíření sady Visual Studio

Rozšíření sady Visual Studio jsou balíčky kódu, které v prostředí Visual Studio a které poskytují nové nebo vylepšené funkce aplikace Visual Studio. Můžete najít další informace o rozšíření sady Visual Studio tady: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

::: moniker range="vs-2017"

Použití **rozšíření a aktualizace** dialogové okno pro instalaci a správu rozšíření sady Visual Studio. Chcete-li otevřít **rozšíření a aktualizace** dialogovém okně zvolte **nástroje** > **rozšíření a aktualizace**, nebo typ **rozšíření** v **Snadné spuštění** vyhledávacího pole.

::: moniker-end

::: moniker range=">=vs-2019"

Použití **spravovat rozšíření** dialogové okno pro instalaci a správu rozšíření sady Visual Studio. Chcete-li otevřít **spravovat rozšíření** dialogovém okně zvolte **rozšíření** > **spravovat rozšíření**. Nebo zadejte **rozšíření** do vyhledávacího pole a tlačítko **spravovat rozšíření**.

::: moniker-end

![Okno rozšíření v sadě Visual Studio](media/finding-using-visual-studio-extensions/extensions-and-updates.png)

V podokně na levé straně rozšíření slouží ke kategorizaci podle těch, které jsou nainstalovány, které jsou dostupné na webu Visual Studio Marketplace (**Online**) a ty, které jsou dostupné aktualizace. **Správce rozšíření pro roaming** udržuje seznam rozšíření sady Visual Studio nainstalujete na počítači nebo instanci sady Visual Studio. Je navržen tak, abyste mohli snadněji najít vaše oblíbená rozšíření.

## <a name="find-visual-studio-extensions"></a>Najít rozšíření sady Visual Studio

Můžete nainstalovat rozšíření z [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs). Rozšíření mohou být ovládací prvky, ukázky, šablony, nástroje nebo jiné součásti, které přidávají funkcionalitu do aplikace Visual Studio. Visual Studio podporuje rozšíření ve formátu balíčku VSIX – to zahrnuje šablony projektu, šablony položek, položky **nástrojů** položky, komponenty spravovaných rozšíření Framework (MEF) a rozšíření VSPackages.

::: moniker range="vs-2017"

Můžete také stáhnout a nainstalovat rozšíření založená na Instalační služby MSI, ale **rozšíření a aktualizace** dialogové okno nelze povolit ani zakázat. Visual Studio Marketplace obsahuje rozšíření VSIX a instalační služby MSI.

::: moniker-end

::: moniker range=">=vs-2019"

Můžete také stáhnout a nainstalovat rozšíření založená na Instalační služby MSI, ale **spravovat rozšíření** dialogové okno nelze povolit ani zakázat. Visual Studio Marketplace obsahuje rozšíření VSIX a instalační služby MSI.

::: moniker-end

## <a name="install-or-uninstall-visual-studio-extensions"></a>Instalace nebo odinstalace rozšíření sady Visual Studio

::: moniker range="vs-2017"

V **rozšíření a aktualizace**, najít rozšíření, které chcete nainstalovat. (Pokud znáte název nebo část názvu rozšíření, je možné hledat **hledání** okna.) Klikněte na tlačítko **Stáhnout**. Rozšíření je naplánovaná instalace. Rozšíření se nainstaluje, když jsou uzavřeny všechny instance sady Visual Studio.

Pokud se pokusíte nainstalovat rozšíření, která obsahuje závislosti, instalační služba zkontroluje, zda jsou již tyto závislosti nainstalovány. Pokud tyto produkty nejsou nainstalovány, **rozšíření a aktualizace** dialogové okno obsahuje závislosti, které je třeba nainstalovat před instalací rozšíření.

::: moniker-end

::: moniker range=">=vs-2019"

V **spravovat rozšíření**, najít rozšíření, které chcete nainstalovat. (Pokud znáte název nebo část názvu rozšíření, je možné hledat **hledání** okna.) Klikněte na tlačítko **Stáhnout**. Rozšíření je naplánovaná instalace. Rozšíření se nainstaluje, když jsou uzavřeny všechny instance sady Visual Studio.

Pokud se pokusíte nainstalovat rozšíření, která obsahuje závislosti, instalační služba zkontroluje, zda jsou již tyto závislosti nainstalovány. Pokud tyto produkty nejsou nainstalovány, **spravovat rozšíření** dialogové okno obsahuje závislosti, které je třeba nainstalovat před instalací rozšíření.

::: moniker-end

Pokud chcete přestat používat rozšíření, lze jej zakázat nebo odinstalovat. Zakázáním rozšíření zůstane rozšíření nainstalováno, ale nedojde k jeho načtení. Můžete zakázat pouze rozšíření VSIX; rozšíření, které jsou nainstalované s použitím Instalační služba MSI lze pouze odinstalovat. Najít rozšíření a klikněte na tlačítko **odinstalovat** nebo **zakázat**. Restartujte sadu Visual Studio pro uvolnění zakázaného rozšíření.

## <a name="per-user-and-administrative-extensions"></a>Za uživatele a administrativní rozšíření

Většina rozšíření jsou rozšíření vázaná na uživatele a jsou nainstalovaná v *%LocalAppData%\Microsoft\VisualStudio\\< verze sady Visual Studio\>\Extensions\\*  složky. Několik rozšíření jsou administrativní rozšíření a jsou nainstalovaná v *\<instalační složky sady Visual Studio > \Common7\IDE\Extensions\\* složky.

Pro ochranu systému proti rozšíření, které mohou obsahovat chyby nebo škodlivý kód, můžete omezit rozšíření vázaná na uživatele pro načtení pouze při spuštění sady Visual Studio s oprávněními běžných uživatelů. To znamená, že je zakázáno rozšíření vázaná na uživatele, při spuštění sady Visual Studio s oprávněními správce. Chcete-li to provést, přejděte na stránku možnosti rozšíření (**nástroje** > **možnosti** > **prostředí**  >   **Rozšíření**). Zrušte **načítání rozšíření pro jednotlivé uživatele při spuštění jako správce** zaškrtněte políčko a potom restartujte Visual Studio.

## <a name="automatic-extension-updates"></a>Aktualizace automatické rozšíření

Rozšíření se automaticky aktualizují, když na webu Visual Studio Marketplace je k dispozici nová verze. Nová verze rozšíření rozpoznán a nainstalován na pozadí. Při příštím otevření sady Visual Studio novou verzi rozšíření používat.

Pokud chcete zakázat automatické aktualizace, můžete zakázat funkci pro všechny přípony nebo pouze konkrétní rozšíření.

::: moniker range="vs-2017"

- Chcete-li zakázat automatické aktualizace pro všechna rozšíření, zvolte **změnit nastavení rozšíření a aktualizace** odkaz v **rozšíření a aktualizace** dialogového okna. V **možnosti** dialogového okna, zrušte zaškrtnutí políčka **automatické aktualizace rozšíření**.

- Chcete-li zakázat automatické aktualizace pro konkrétní příponu, zrušte zaškrtnutí políčka **automaticky aktualizovat toto rozšíření** možnost v podokně podrobností rozšíření na pravé straně **rozšíření a aktualizace** dialogového okna.

::: moniker-end

::: moniker range=">=vs-2019"

- Chcete-li zakázat automatické aktualizace pro všechna rozšíření, zvolte **změnit nastavení pro rozšíření** odkaz v **spravovat rozšíření** dialogového okna. V **možnosti** dialogového okna, zrušte zaškrtnutí políčka **automatické aktualizace rozšíření**.

- Chcete-li zakázat automatické aktualizace pro konkrétní příponu, zrušte zaškrtnutí políčka **automaticky aktualizovat toto rozšíření** možnost v podokně podrobností rozšíření na pravé straně **spravovat rozšíření** dialogového okna.

::: moniker-end

## <a name="extension-crash-and-unresponsiveness-notifications"></a>Oznámení o chybách a sekundový výpadek reakce rozšíření

Visual Studio vás upozorní, pokud má podezření, že rozšíření byl zahrnut v chybě během předchozí relace. Pokud dojde k chybě sady Visual Studio, ukládá zásobník výjimek. Při příštím spuštění Visual Studio zjistí zásobníku, počínaje listu a funguje směrem k základní třídě. Pokud Visual Studio zjistí, že blok patří do modulu, který je součástí rozšíření nainstalované a povolené, zobrazuje oznámení o.

Visual Studio také vás upozorní, pokud ji má podezření, že rozšíření je příčinou uživatelského rozhraní za nereagujícího.

Když tato oznámení jsou zobrazeny, můžete ignorovat oznámení nebo Absolvujte některou z následujících akcí:

::: moniker range="vs-2017"

- Zvolte **zakázat toto rozšíření**. Visual Studio zakáže rozšíření a poznáte, jestli je potřeba restartovat systém pro zakázání se projeví. Můžete znovu povolit doplněk **rozšíření a aktualizace** dialogovému oknu, chcete-li.

::: moniker-end

::: moniker range=">=vs-2019"

- Zvolte **zakázat toto rozšíření**. Visual Studio zakáže rozšíření a poznáte, jestli je potřeba restartovat systém pro zakázání se projeví. Můžete znovu povolit doplněk **spravovat rozšíření** dialogovému oknu, chcete-li.

::: moniker-end

- Zvolte **tuto zprávu již nezobrazovat**.

  - Pokud oznámení týká chybovému ukončení v předchozí relaci, sada Visual Studio už zobrazí oznámení, když se chyby spojené s toto rozšíření vyvolá. Visual Studio bude stále zobrazovat upozornění při zablokování můžou být spojené s touto příponou nebo zhroucení nebo zablokování, která můžou být spojené s další rozšíření.
  - Oznámení týká sekundový výpadek reakce, rozhraní IDE přestane zobrazovat oznámení při toto rozšíření je přidružen sekundový výpadek reakce. Visual Studio se stále zobrazí oznámení týkající se chyb pro tuto příponu a při selhání a zablokování související upozornění pro další rozšíření.

- Zvolte **Další** na této stránce.

- Zvolte **X** tlačítko na konci oznámení zavřete oznámení. Zobrazí se nové oznámení pro budoucí instance rozšíření jsou spojeny s zhroucení nebo zablokování uživatelského rozhraní.

> [!NOTE]
> Uživatelské rozhraní sekundový výpadek reakce nebo selhání oznámení znamená, že pouze jeden z tohoto rozšíření modulů v zásobníku byl při reagovat uživatelské rozhraní, nebo když došlo k selhání. To neznamená, že rozšíření samotné bylo nadměrné spotřeby. Je možné, že rozšíření volat kód, který je součástí sady Visual Studio, které zase přestal reagovat uživatelské rozhraní nebo selhání. Však oznámení může být stále užitečná, pokud rozšíření, která vedla k zablokování uživatelského rozhraní nebo při selhání není pro vás důležité. V takovém případě při zakázání rozšíření zabráněno zablokování uživatelského rozhraní nebo selhání v budoucnu, bez dopadu na vaši produktivitu.

## <a name="sample-master-copies-and-working-copies"></a>Ukázka hlavní kopie a pracovní kopie

Při instalaci online ukázky je řešení uloženo na dvou místech:

- Pracovní kopie je uložena v umístění, které jste zadali při vytváření projektu.

- Samostatná hlavní kopie je uložena v počítači.

::: moniker range="vs-2017"

Můžete použít **rozšíření a aktualizace** okna k provedení těchto úloh týkajících se ukázek:

::: moniker-end

::: moniker range=">=vs-2019"

Můžete použít **spravovat rozšíření** okna k provedení těchto úloh týkajících se ukázek:

::: moniker-end

- Zobrazit seznam hlavních kopií ukázek, které jste nainstalovali.

- Zakázat nebo odinstalovat hlavní kopii ukázky.

- Instalovat balíky ukázek, což jsou kolekce ukázek, které se týkají technologie nebo funkce.

- Nainstalujte jednotlivé online ukázky.

- Zobrazit upozornění na aktualizace při zveřejnění změny zdrojového kódu nainstalovaných ukázek.

- Aktualizujte hlavní kopii nainstalované ukázky, když je oznámení o aktualizaci.

::: moniker range="vs-2017"

## <a name="installing-without-using-the-extensions-and-updates-dialog-box"></a>Instalace bez použití dialogovém okně rozšíření a aktualizace

Rozšíření, která byla zabalena v souboru *VSIX* soubory mohou být k dispozici v jiném umístění než Visual Studio Marketplace. **Rozšíření a aktualizace** dialogové okno nelze rozpoznat tyto soubory, ale můžete nainstalovat *VSIX* soubor poklikáte soubor nebo výběr souboru a stisknutím klávesy **Enter**klíč. Potom postupujte podle pokynů. Pokud je rozšíření nainstalované, můžete použít **rozšíření a aktualizace** dialogové okno povolit, zakázat nebo ho odinstalujte.

## <a name="extension-types-not-supported-by-the-extensions-and-updates-dialog-box"></a>Rozšíření typy nejsou podporovány v dialogovém okně rozšíření a aktualizace

Visual Studio i nadále podporuje rozšíření, které instaluje Microsoft Installer (MSI) ale není až **rozšíření a aktualizace** dialogové okno bez úprav.

> [!TIP]
> Pokud obsahuje rozšíření na základě Instalační služby MSI *extension.vsixmanifest* souboru, zobrazí se v rozšíření **rozšíření a aktualizace** dialogové okno.

::: moniker-end

::: moniker range=">=vs-2019"

## <a name="installing-without-using-the-manage-extensions-dialog-box"></a>Instalace bez pomocí dialogového okna Spravovat rozšíření

Rozšíření, která byla zabalena v souboru *VSIX* soubory mohou být k dispozici v jiném umístění než Visual Studio Marketplace. **Spravovat rozšíření** dialogové okno nelze rozpoznat tyto soubory, ale můžete nainstalovat *VSIX* soubor poklikáte soubor nebo výběr souboru a stisknutím klávesy **Enter** klíč. Potom postupujte podle pokynů. Pokud je rozšíření nainstalované, můžete použít **spravovat rozšíření** dialogové okno povolit, zakázat nebo ho odinstalujte.

## <a name="extension-types-not-supported-by-the-manage-extensions-dialog-box"></a>Rozšíření typy nejsou podporovány v dialogovém okně Spravovat rozšíření

Visual Studio i nadále podporuje rozšíření, které instaluje Microsoft Installer (MSI) ale není až **spravovat rozšíření** dialogové okno bez úprav.

> [!TIP]
> Pokud obsahuje rozšíření na základě Instalační služby MSI *extension.vsixmanifest* souboru, zobrazí se v rozšíření **spravovat rozšíření** dialogové okno.

::: moniker-end