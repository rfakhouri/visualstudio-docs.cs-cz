---
title: Projekty a řešení – dialogové okno Možnosti
ms.date: 07/14/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.General
- VS.ToolsOptionsPages.Projects.Locations
helpviewer_keywords:
- Projects and Solutions Options dialog box
- Options dialog box, Projects and Solutions
ms.assetid: 2801f24e-a138-488a-ae3c-e1f99a678ac0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dbd3fe20377cd2aa4954e904fec50702cc9b7120
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34843988"
---
# <a name="projects-and-solutions-page-options-dialog-box"></a>Projekty a řešení stránky, dialogové okno Možnosti

Nastaví chování sady Visual Studio související s projekty a řešení. Chcete-li získat přístup k tyto možnosti, vyberte **nástroje** > **možnosti**, rozbalte položku **projekty a řešení**a potom vyberte **Obecné** .

Do výchozích cest pro projekt a šablony složky jsou nastaveny prostřednictvím **umístění** karta v dialogovém okně stejné.

> [!NOTE]
> Možnosti dostupné v uživatelském rozhraní může lišit od co je zde popsán v závislosti na aktivním nastavení nebo edici. Tento článek byl napsán s **Obecné vývojové nastavení** v paměti. Chcete-li zobrazit nebo změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="general-page"></a>Obecná stránka

Tyto možnosti jsou dostupné na **Obecné** stránky.

### <a name="always-show-error-list-if-build-finishes-with-errors"></a>Vždy zobrazovat seznam chyb Pokud sestavení dokončena s chybami

Otevře se **seznam chyb** okno na dokončení sestavení, pouze v případě, že projektu se nepovedlo sestavit. Zobrazí se chyby, ke kterým došlo během procesu vytváření. Pokud tato možnost vybrána, stále dojít k chybám, ale okno neotevře po dokončení sestavení. Tato možnost je povolená ve výchozím nastavení.

### <a name="track-active-item-in-solution-explorer"></a>Sledování active položky v Průzkumníku řešení

Při výběru **Průzkumníku řešení** automaticky otevře a aktivní položka vybrána. Vybraná položka změny jako můžete spolupracovat s různé soubory v projektu nebo řešení nebo různých komponent v návrháři. Pokud tato možnost vybrána, výběr v **Průzkumníku řešení** automaticky nezmění. Tato možnost je povolená ve výchozím nastavení.

### <a name="show-advanced-build-configurations"></a>Zobrazit upřesněné konfigurace sestavení

Při výběru možností konfigurace sestavení zobrazí na **stránek vlastností projektu** dialogové okno a **stránky vlastností řešení** dialogové okno. Při zaškrtnutí políčka zrušeno, možnosti konfigurace sestavení nejsou zobrazeny na **stránek vlastností projektu** dialogové okno a **stránky vlastností řešení** dialogové okno pro projekty Visual Basic a C#, které obsahují jednu konfigurace nebo dvě konfigurace ladění a vydání. Pokud projekt má konfiguraci definovaný uživatelem, jsou uvedeny možnosti konfigurace sestavení.

Když není vybraná, příkazy na **sestavení** nabídky, například **sestavit řešení**, **znovu sestavit řešení**, a **Vyčistit řešení**, jsou v konfiguraci verze a příkazy provést na **ladění** nabídky, například **spustit ladění** a **spustit bez ladění**, se provádí na Konfigurace ladění.

### <a name="always-show-solution"></a>Vždy zobrazovat řešení

Při výběru řešení a všechny příkazy, které fungují v řešení jsou vždy zobrazeny v prostředí IDE. Při zaškrtnutí políčka zrušeno, všechny projekty jsou vytvořeny jako samostatné projekty a nevidíte řešení v Průzkumníku řešení nebo příkazy, které fungují na řešení v prostředí IDE Pokud řešení obsahuje pouze jeden projekt.

### <a name="save-new-projects-when-created"></a>Uložit nové projekty při vytvoření

Pokud vybraná, můžete zadat umístění pro svůj projekt v **nový projekt** dialogové okno. Není-li zaškrtnuto, jsou všechny nové projekty vytvořené jako dočasné projekty. Při práci s dočasné projekty, můžete vytvořit a experimentovat s projektem bez nutnosti zadávat umístění na disku.

### <a name="warn-user-when-the-project-location-is-not-trusted"></a>Upozornit uživatele, když umístění projektu není důvěryhodné

Pokud se pokusíte vytvořit nový projekt nebo otevřít existující projekt v umístění, které není plně důvěryhodný (například na cestu UNC nebo HTTP), zobrazí se zpráva. Tuto možnost použijte k určení, zda zpráva se zobrazí pokaždé, když se pokusíte vytvořit nebo otevřít projekt v umístění, které není plně důvěryhodný.

### <a name="show-output-window-when-build-starts"></a>Při spuštění sestavení zobrazit výstup – okno

Automaticky zobrazí [výstup – okno](../../ide/reference/output-window.md) v integrovaném vývojovém prostředí od počátku řešení sestavení.

### <a name="prompt-for-symbolic-renaming-when-renaming-files"></a>Vyzvat, aby symbolický přejmenování při přejmenování souborů

Pokud vybraná, Visual Studio zobrazí okno zprávy s dotazem, zda je také přejmenujte všechny odkazy v projektu na tento element kódu.

### <a name="prompt-before-moving-files-to-a-new-location"></a>Výzvu před přesunutím soubory do nového umístění

Při výběru, Visual Studio zobrazí potvrzovací okno se zprávou, než jsou změnit umístění souborů akcemi v **Průzkumníku řešení**.

### <a name="reopen-documents-on-solution-load"></a>Znovu otevřít dokumenty na zatížení řešení

**Nové ve verzi Visual Studio 2017 15.8 verze preview 2 nebo novější**

Při výběru, jsou dokumenty, které byly ponechány otevřené předchozí doba řešení bylo ukončeno automaticky otevře při řešení je otevřen.

Znovu určité typy souborů nebo návrháři zpozdit zatížení řešení. Tuto možnost, zrušte zaškrtnutí políčka [zlepšit výkon zatížení řešení](../../ide/visual-studio-performance-tips-and-tricks.md#disable-automatic-file-restore) Pokud nechcete obnovit předchozí kontext na řešení.

## <a name="locations-page"></a>Stránka umístění

Tyto možnosti jsou dostupné na **umístění** stránky.

### <a name="projects-location"></a>Projekty umístění

Určuje výchozí umístění, kde Visual Studio vytvoří nové projekty a řešení složky. Několik dialogových oken také použít tak umístění, nastavte tuto možnost pro složku počáteční body. Například **otevřeného projektu** dialogové okno používá toto umístění **projekty** zástupce.

### <a name="user-project-templates-location"></a>Umístění šablon projektů uživatele

Určuje výchozí umístění, **nový projekt** dialogové okno se používá k vytvoření seznamu **šablony**. Další informace najdete v tématu [postupy: vyhledání a uspořádání šablony](../../ide/how-to-locate-and-organize-project-and-item-templates.md).

### <a name="user-item-templates-location"></a>Uživatelské umístění šablon

Určuje výchozí umístění, **přidat novou položku** dialogové okno se používá k vytvoření seznamu **šablony**. Další informace najdete v tématu [postupy: vyhledání a uspořádání šablony](../../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>Viz také:

- [Dialogové okno Možnosti, projekty a řešení, sestavit a spustit](../../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- [Dialogové okno Možnosti, projekty a řešení, webové projekty](../../ide/reference/options-dialog-box-projects-and-solutions-web-projects.md)
