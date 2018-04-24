---
title: Správa vlastností projektů a řešení
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 75247EB8-323A-4AFD-A451-6703A03D5D1F
ms.openlocfilehash: c4d4366843a6ea07286c73810f821b41f95e44b9
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="managing-project-and-solution-properties"></a>Správa vlastností projektů a řešení

## <a name="project-options"></a>Možnosti projektu

Možnosti projektu jsou specifické pro každý projekt a vliv na způsob zapisovat, vytvořené a spustit projekt. Tím se liší od sady Visual Studio pro Mac Předvolby (který nastaví možnosti specifické pro uživatele) a možnosti řešení (které nastavte možnosti pro celé řešení). Možnosti projektu jsou uloženy v souboru projektu (.csproj) tak, aby ostatní vývojáři můžete sestavit a spustit projekt správně. Možnosti konkrétní projektu umožní celá řada vývojářů pro práci na stejném dokumentu bez kompromisů formátování souboru.

Otevřete projekt možnosti v sadě Visual Studio pro Mac dvakrát klikněte na název projektu, nebo klikněte pravým tlačítkem a otevřete kontextu nabídku a vyberte **možnosti**:

 ![V místní nabídce možnost](media/projects-and-solutions-image2.png)

Upravitelné možnosti zahrnují možnosti pro vytvoření, spuštění a nastavte zdrojový kód a možnosti správy verzí.

Možnosti projektu jsou uspořádány do pěti různých kategorií:

* **Obecné** -informace o projektu, například název, popis a výchozí Namespace nastaveny zde, společně s umístění projektu.
* **Sestavení** – to umožňuje vývojáři nastavit nebo změnit PCL profily pro přenosné knihovny tříd. Umožňuje také pro vlastní příkazy, konfigurace, – možnosti kompilátoru nastavit. Název a cesta k sestavení výstupu můžete nastavit také zde.
* **Spustit** – to vám umožní vytvořit vlastní konfigurace pro spuštění na jednotlivých projektů.
* **Zdrojový kód** – toto umožňuje řídit formátování mnoha různých typů souborů a konvence vytváření názvů. Můžete vytvořit také pojmenování zásady a výchozí styly záhlaví sem.
* **Správa verzí** – to slouží k úpravě stylu potvrzení zprávy při použití správy verzí s projektem.

Každý projekt, může obsahovat možnosti konkrétní projektu, v závislosti na platformu. Například projektu Xamarin.Android, stejný, jako je znázorněno na následujícím obrázku má možnosti týkající se systémem Android sestavení – například možnosti linkeru; a aplikace – například oprávnění:

 ![Možnosti projektu pro Android](media/projects-and-solutions-image5.png)

Xamarin.iOS má možnosti související k podepisování sady – například požadovaný profil zřizování se mají použít:

 ![iOS možnosti projektu](media/projects-and-solutions-image6.png)

## <a name="solution-options"></a>Možnosti řešení 

Možnosti řešení jsou podobné možnosti projektu, ale zahrnují oboru celého řešení. Poskytují způsob, jak nastavit informace o autorovi, nastavení, kód formátování styly a správa verzí sestavení a umožňují pro způsob, jak přiřadit spouštěný projekt v řešení.  Dialogové okno Možnosti řešení je přístupná z **Projekt > Možnosti řešení** položky nabídky z **možnosti** položky kontextové nabídky na řešení v panelu pro řešení, nebo dvojím kliknutím na Řešení v panelu pro řešení:

 ![Možnosti řešení](media/projects-and-solutions-image7.png)
