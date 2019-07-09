---
title: Správa vlastností projektů a řešení
description: Tento článek popisuje, jak Správa vlastností projektů a řešení v sadě Visual Studio pro Mac
author: heiligerdankgesang
ms.author: dominicn
ms.date: 05/06/2018
ms.assetid: 75247EB8-323A-4AFD-A451-6703A03D5D1F
ms.openlocfilehash: 514792804515541b7e4f64359a08e9c6093c5018
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2019
ms.locfileid: "67692873"
---
# <a name="managing-project-and-solution-properties"></a>Správa vlastností projektů a řešení

## <a name="project-options"></a>Možnosti projektu

Možnosti projektu jsou specifická pro každý projekt a ovlivnit jak napsané, vytvoření a spuštění projektu. Tím se liší od sady Visual Studio pro Mac Předvolby (který nastaví možnosti specifické pro uživatele) a možnosti řešení (které nastavení možností pro celé řešení). Možnosti projektu jsou uloženy v souboru projektu (.csproj) tak, aby ostatní vývojáři můžete sestavit a spustit projekt správně. Možnosti určitého projektu umožňuje celá řada vývojářů pro práci na stejný dokument bez negativního vlivu formátování souboru.

Chcete-li otevřít panel Možnosti projektu v sadě Visual Studio pro Mac, dvakrát klikněte na název projektu, nebo klikněte pravým tlačítkem na otevřete kontextovou nabídku a vyberte **možnosti**:

![V kontextové nabídce](media/projects-and-solutions-image2.png)

Upravit možnosti zahrnují možnosti, jak sestavit, spusťte a nastavte zdrojový kód a správou verzí.

Možnosti projektu jsou uspořádány do pěti různých kategorií:

* **Obecné** – informace o projektu, jako je název, popis a výchozí Namespace jsou nastaveny, společně s umístěním projektu.
* **Sestavení** – to umožňuje vývojářům nastavení nebo změna PCL profily pro přenosné knihovny tříd. Umožňuje také pro vlastní příkazy, konfigurace a možnosti kompilátoru, která se má nastavit. Název a cesta k sestavení výstupu můžete nastavit také zde.
* **Spustit** – díky tomu můžete vytvořit vlastní konfigurace spuštění na základě jednotlivých projektů.
* **Zdrojový kód** – toto umožňuje řídit formátování mnoha různých typů souborů a zásady vytváření názvů. Můžete vytvořit také zásady vytváření názvů a výchozí styly záhlaví tady.
* **Správa verzí** – díky tomu můžete upravit styl zprávy potvrzení změn, při použití správy verzí s projektem.

Každý projekt může obsahovat možnosti určitého projektu, v závislosti na platformě. Například projekt Xamarin.Android, jako je ten, který je znázorněn na následujícím obrázku má možnosti týkající se Androidu sestavení (například možnosti linkeru) a aplikací (například oprávnění):

![Možnosti projektu pro Android](media/projects-and-solutions-image5.png)

Xamarin.iOS má možnosti týkající se k podepsání sady prostředků – například požadovaný zřizovací profil:

![iOS možnosti projektu](media/projects-and-solutions-image6.png)

## <a name="solution-options"></a>Možnosti řešení

Možnosti řešení jsou podobné možnosti projektu, ale zahrnují oboru celé řešení. Poskytují způsob, jak nastavit informace o autorovi, nastavení, kód formátování styly a správu verzí, sestavení a umožňují pro způsob, jak přiřadit spouštěný projekt v řešení.  V dialogovém okně Možnosti řešení je přístupný z **Projekt > Možnosti řešení** položku nabídky z **možnosti** položka kontextové nabídky na řešení v oblasti řešení nebo poklikáním na Řešení v oblasti řešení:

![Možnosti řešení](media/projects-and-solutions-image7.png)

## <a name="see-also"></a>Viz také:

* [Správa vlastností projektů a řešení (Visual Studio na Windows)](/visualstudio/ide/managing-project-and-solution-properties)