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
ms.openlocfilehash: 631b9fc17345d5d0c00d36e42a9d3b1db633c114
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="projects-and-solutions-options-dialog-box"></a>Projekty a řešení – dialogové okno Možnosti
Nastaví [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] chování související s projekty a řešení. Chcete-li získat přístup k tyto možnosti, vyberte **nástroje > Možnosti** rozbalte **projekty a řešení**a klikněte na tlačítko **Obecné**.

Do výchozích cest pro projekt a šablony složky jsou nastaveny prostřednictvím **umístění** karta v dialogovém okně stejné.

> [!NOTE]
> K dispozici v dialogových oken, názvy a umístění příkazy nabídky, které vidíte, se může lišit od co je popsáno v nápovědě v závislosti na aktivním nastavení nebo edici. Tato stránka nápovědy byla zapsána s **Obecné vývojové nastavení** v paměti. Chcete-li zobrazit nebo změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).


## <a name="general-tab-options"></a>Karta Obecné možnosti

**Vždy zobrazovat seznam chyb Pokud sestavení dokončena s chybami**

Otevře se **seznam chyb** okno na dokončení sestavení, pouze v případě, že projektu se nepovedlo sestavit. Zobrazí se chyby, ke kterým došlo během procesu vytváření. Pokud tato možnost vybrána, stále dojít k chybám, ale okno neotevře po dokončení sestavení. Tato možnost je povolená ve výchozím nastavení.

**Sledování Active položky v Průzkumníku řešení**

Při výběru **Průzkumníku řešení** automaticky otevře a aktivní položka vybrána. Vybraná položka změny jako můžete spolupracovat s různé soubory v projektu nebo řešení nebo různých komponent v návrháři. Pokud tato možnost vybrána, výběr v **Průzkumníku řešení** automaticky nezmění. Tato možnost je povolená ve výchozím nastavení.

**Zobrazit upřesněné konfigurace sestavení**

Při výběru možností konfigurace sestavení zobrazí na **stránek vlastností projektu** dialogové okno a **stránky vlastností řešení** dialogové okno. Při zaškrtnutí políčka zrušeno, možnosti konfigurace sestavení nejsou zobrazeny na **stránek vlastností projektu** dialogové okno a **stránky vlastností řešení** dialogové okno pro [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] a [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] projekty obsahující jednu konfiguraci nebo dvě konfigurace debug a release. Pokud projekt má konfiguraci definovaný uživatelem, jsou uvedeny možnosti konfigurace sestavení.

Když není vybraná, příkazy na **sestavení** nabídky, například **sestavit řešení**, **znovu sestavit řešení**, a **Vyčistit řešení**, jsou v konfiguraci verze a příkazy provést na **ladění** nabídky, například **spustit ladění** a **spustit bez ladění**, se provádí na Konfigurace ladění.

**Vždy zobrazovat řešení**

Při výběru řešení a všechny příkazy, které fungují v řešení jsou vždy zobrazeny v prostředí IDE. Při zaškrtnutí políčka zrušeno, všechny projekty jsou vytvořeny jako samostatné projekty a nevidíte řešení v Průzkumníku řešení nebo příkazy, které fungují na řešení v prostředí IDE Pokud řešení obsahuje pouze jeden projekt.

**Uložit nové projekty při vytvoření**

Pokud vybraná, můžete zadat umístění pro svůj projekt v **nový projekt** dialogové okno. Není-li zaškrtnuto, jsou všechny nové projekty vytvořené jako dočasné projekty. Při práci s dočasné projekty, můžete vytvořit a experimentovat s projektem bez nutnosti zadávat umístění na disku.

**Upozornit uživatele, když umístění projektu není důvěryhodné**

Pokud se pokusíte vytvořit nový projekt nebo otevřít existující projekt v umístění, které není plně důvěryhodný (například na cestu UNC nebo HTTP), zobrazí se zpráva. Tuto možnost použijte k určení, zda zpráva se zobrazí pokaždé, když se pokusíte vytvořit nebo otevřít projekt v umístění, které není plně důvěryhodný.

**Při spuštění sestavení zobrazit výstup – okno**

Automaticky zobrazí ve výstupním okně v integrovaném vývojovém prostředí od počátku řešení sestavení. Další informace najdete v tématu [postupy: řízení ve výstupním okně](http://msdn.microsoft.com/Library/91aebd15-8854-4a7a-9f7d-57376fb4e858).

**Vyzvat, aby symbolický přejmenování při přejmenování souborů**

Při výběru [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zobrazí pole zpráva s dotazem, zda je také přejmenujte všechny odkazy v projektu na tento element kódu.

**Výzvu před přesunutím soubory do nového umístění**

Při výběru [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zobrazí potvrzovací okno se zprávou, než jsou akcemi v Průzkumníku řešení změnit umístění souborů.

**Znovu otevřít dokumenty na zatížení řešení (Visual Studio 2017 verze 15.8 verze preview 2 a novější)**
 
Při načítání řešení automaticky znovu otevřete dokumenty, které byly otevřít v předchozí relace. Při výběru, jsou dokumenty, které byly otevřené předchozí době, kdy bylo ukončeno toto řešení automaticky otevře při načtení řešení.

Znovu určité typy souborů nebo návrháři zpozdit zatížení řešení. Tuto možnost, chcete-li zvýšit výkon zatížení řešení, pokud nechcete obnovit předchozí kontext na řešení, zrušte zaškrtnutí.

## <a name="locations-tab-options"></a>Umístění karta Možnosti

**Projekty umístění**

Určuje výchozí umístění kde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vytvoří nové projekty a řešení složky. Několik dialogových oken také použít tak umístění, nastavte tuto možnost pro složku počáteční body. Například dialogové okno Otevřít projekt používá toto umístění pro moje projekty zástupce.

**Umístění šablon projektů uživatele**

Určuje výchozí umístění, **nový projekt** dialogové okno se používá k vytvoření seznamu **šablony**. Další informace najdete v tématu [postupy: vyhledání a uspořádání šablony](../../ide/how-to-locate-and-organize-project-and-item-templates.md).

**Uživatelské umístění šablon**

Určuje výchozí umístění, **přidat novou položku** dialogové okno se používá k vytvoření seznamu **šablony**. Další informace najdete v tématu [postupy: vyhledání a uspořádání šablony](../../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>Viz také

- [Dialogové okno Možnosti, projekty a řešení, sestavit a spustit](../../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- [Dialogové okno Možnosti, projekty a řešení, webové projekty](../../ide/reference/options-dialog-box-projects-and-solutions-web-projects.md)
