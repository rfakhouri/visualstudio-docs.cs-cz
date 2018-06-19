---
title: 'Postupy: vytvoření a úprava konfigurací'
ms.date: 06/21/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- solution build configurations, editing
- build configurations, creating
- solution build configurations, creating
- build configurations, editing
- builds [Visual Studio], setting up
- property pages
- Configuration Manager
- project build configurations, creating
- project build configurations, editing
ms.assetid: 19be121c-148e-4ece-bbfc-d20b08cfc3f7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3aa3aaa197f392d300e8787d582314846e789f47
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946309"
---
# <a name="how-to-create-and-edit-configurations"></a>Postupy: vytvoření a úprava konfigurací

Můžete vytvořit několik konfigurace sestavení řešení. Například můžete nakonfigurovat sestavení ladicí verze, která vaše testery vám pomůže najít a opravit problémy, a můžete nakonfigurovat různé druhy sestavení, které můžete distribuovat do různých zákazníků.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="create-build-configurations"></a>Vytvoření konfigurace sestavení

Můžete použít **nástroje Configuration Manager** dialogové okno Vybrat nebo upravit existující konfigurace sestavení nebo vytvořit nové.

Otevřete **nástroje Configuration Manager** dialogu **Průzkumníku řešení**, otevřete místní nabídku pro řešení a zvolte **nástroje Configuration Manager**.

> [!NOTE]
> Pokud **nástroje Configuration Manager** příkaz se nezobrazí v místní nabídce, vyhledejte v části **sestavení** nabídky v řádku nabídek. Pokud se nezobrazí existuje buď v řádku nabídek zvolte **nástroje** > **možnosti**a potom v levém podokně **možnosti** dialogové okno, rozbalte seznam **Projekty a řešení** > **Obecné**a v pravém podokně, vyberte **zobrazit Rozšířená konfigurace sestavení** zaškrtávací políčko.

V **nástroje Configuration Manager** dialogové okno, můžete použít **aktivní konfigurace řešení** rozevíracího seznamu vyberte položku konfigurace sestavení řešení celou, upravit existující nebo vytvořit nový konfigurace. Můžete použít **platforma Active řešení** rozevíracího seznamu vyberte platformu, konfigurace cílí upravit existující, nebo přidat nové platformě. **Projektu kontexty** podokně zobrazí projekty v řešení. Pro každý projekt můžete vyberte platformu a konfigurace specifické pro projekt, upravit existující, nebo vytvořit novou konfiguraci nebo přidat nové platformě. Můžete také vybrat políček, která označuje, zda každý projekt zahrnuty při použití konfigurace celé řešení k sestavení nebo nasazení řešení.

 Po nastavení konfigurace, které chcete, můžete nastavit vlastnosti projektu, které jsou vhodné pro tyto konfigurace.

### <a name="to-set-properties-based-on-configurations"></a>Nastavení vlastností na základě konfigurací

-   V **Průzkumníku řešení**, otevřete místní nabídky pro projekt a zvolte **vlastnosti**.

     **Stránky vlastností** otevře se okno.

     Nastavení vlastností pro vaše konfigurace. Například pro konfiguraci vydání, můžete zadat, když je integrované řešení, a pro konfiguraci ladění, můžete určit, že je optimalizovaný kód `DEBUG` symbol Podmíněná kompilace je součástí. Další informace o nastavení vlastnosti stránky najdete v tématu [spravovat vlastnosti projektu a řešení](../ide/managing-project-and-solution-properties.md).

## <a name="create-and-modify-project-configurations"></a>Vytvoření a změna konfigurace projektu

### <a name="to-create-a-project-configuration"></a>Pro vytvoření konfigurace projektu

1.  Otevřete **nástroje Configuration Manager** dialogové okno.

2.  Vyberte projekt v **projektu** sloupce.

3.  V **konfigurace** rozevíracího seznamu pro tento projekt, vyberte **nový**.

     **Novou konfiguraci projektu** otevře se dialogové okno.

4.  V **název** pole, zadejte název pro novou konfiguraci.

5.  Pro použití s nastavením vlastnosti z existující konfigurace projektu, v **Kopírovat nastavení z** rozevíracího seznamu, vyberte takovou konfiguraci.

6.  Chcete-li vytvořit řešení celou konfiguraci ve stejnou dobu, vyberte **vytvořit novou konfiguraci řešení** zaškrtávací políčko.

### <a name="to-rename-a-project-configuration"></a>Chcete-li přejmenovat konfigurace projektu

1.  Otevřete **nástroje Configuration Manager** dialogové okno.

2.  V **projektu** sloupce, vyberte projekt, který má projektu konfiguraci, kterou chcete přejmenovat.

3.  V **konfigurace** rozevíracího seznamu pro tento projekt, vyberte **upravit**.

     **Upravit konfigurace projektu** otevře se dialogové okno.

4.  Vyberte název konfigurace projektu, který chcete změnit.

5.  Vyberte **přejmenovat**a pak zadejte nový název.

## <a name="create-and-modify-solution-wide-build-configurations"></a>Vytvoření a změna konfigurace sestavení řešení celou

### <a name="to-create-a-solution-wide-build-configuration"></a>Pro vytvoření konfigurace sestavení řešení celou

1.  Otevřete **nástroje Configuration Manager** dialogové okno.

2.  V **aktivní konfigurace řešení** rozevíracího seznamu vyberte **nový**.

     **Novou konfiguraci řešení** otevře se dialogové okno.

3.  V **název** textové pole, zadejte název pro novou konfiguraci.

4.  Chcete použít nastavení z existující konfigurace řešení, v **Kopírovat nastavení z** rozevíracího seznamu, vyberte takovou konfiguraci.

5.  Pokud chcete vytvořit konfigurace projektu ve stejnou dobu, vyberte **vytvořit nové konfigurace projektu** zaškrtávací políčko.

### <a name="to-rename-a-solution-wide-build-configuration"></a>Chcete-li přejmenovat řešení celé konfigurace sestavení

1.  Otevřete **nástroje Configuration Manager** dialogové okno.

2.  V **aktivní konfigurace řešení** rozevíracího seznamu vyberte **upravit**.

     **Upravit konfigurace řešení** otevře se dialogové okno.

3.  Vyberte název konfigurace řešení, které chcete změnit.

4.  Vyberte **přejmenovat**a pak zadejte nový název.

### <a name="to-modify-a-solution-wide-build-configuration"></a>Ke změně konfigurace sestavení řešení celou

1.  Otevřete **nástroje Configuration Manager** dialogové okno.

2.  V **aktivní konfigurace řešení** rozevíracího seznamu vyberte konfigurace, kterou chcete.

3.  V **projektu kontexty** podokně, pro každý projekt, vyberte **konfigurace** a **platformy** a vyberte ohledně **sestavení**ho a zda má být **nasadit** ho.

## <a name="see-also"></a>Viz také

- [Pochopení konfigurace sestavení](../ide/understanding-build-configurations.md)
- [Sestavení a čištění projektů a řešení v sadě Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Správa vlastností projektů a řešení](managing-project-and-solution-properties.md)