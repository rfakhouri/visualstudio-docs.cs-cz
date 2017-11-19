---
title: "Správa vlastností projektů a řešení | Microsoft Docs"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 75247EB8-323A-4AFD-A451-6703A03D5D1F
ms.openlocfilehash: 8871ab002a94a9c0bbc0063a25b4dea9cb271142
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="managing-project-and-solution-properties"></a>Správa vlastností projektů a řešení

## <a name="project-options"></a>Možnosti projektu

Možnosti projektu jsou specifické pro každý projekt a vliv na způsob zapisovat, vytvořené a spustit projekt. Tím se liší od pomocí sady Visual Studio pro Mac předvolby, kterou chcete nastavit možnosti specifické pro uživatele, a s možností řešení, které nastavení možností pro celé řešení. Možnosti projektu jsou uloženy v souboru projektu (.csproj) tak, aby ostatní vývojáři můžete sestavit a spustit projekt správně. To umožňuje mnoho vývojářům pracovat na stejné dokumentu, aniž by to ohrozilo formátování souboru.

Projekt možnosti v sadě Visual Studio pro Mac může být spuštěn dvojím kliknutím na název projektu nebo otevření v místní nabídce kliknete pravým tlačítkem a výběrem **možnosti**:

 ![V místní nabídce možnost](media/projects-and-solutions-image2.png)

Upravitelné možnosti zahrnují těch, které chcete vytvořit, spusťte a nastavte možnosti řízení zdrojového kódu a verzi.

Možnosti projektu jsou uspořádány do pěti různých kategorií, které mají následující možnosti:

* **Obecné** -informace o projektu, například název, popis a výchozí Namespace lze nastavit tady, společně s umístění projektu.
* **Sestavení** – to umožňuje vývojáři nastavit nebo změnit PCL profily pro přenosné knihovny tříd. Umožňuje také pro vlastní příkazy, konfigurace, – možnosti kompilátoru nastavit. Název a cesta k sestavení výstupu můžete nastavit také zde.
* **Spustit** – to vám umožní vytvořit vlastní konfigurace pro spuštění na jednotlivých projektů.
* **Zdrojový kód** – toto umožňuje řídit formátování mnoha různých typů souborů a konvence vytváření názvů. Můžete vytvořit také pojmenování zásady a výchozí styly záhlaví sem.
* **Správa verzí** – to slouží k úpravě stylu potvrzení zprávy při použití správy verzí s projektem.

Každý projekt, může také obsahovat možnosti konkrétní projektu, v závislosti na platformu. Například projektu Xamarin.Android, jako je ten, který je zobrazený dole, bude mít možnosti týkající se systémem Android sestavení – například možnosti linkeru; a aplikace – například oprávnění:

 ![Možnosti projektu pro Android](media/projects-and-solutions-image5.png)

Xamarin.iOS bude obsahovat možnosti týkající se k podepisování sady – například požadovaný profil zřizování se použije. a týkající se možnosti balení IPA:

 ![iOS možnosti projektu](media/projects-and-solutions-image6.png)

## <a name="solution-options"></a>Možnosti řešení 

Možnosti řešení jsou podobné možnosti projektu, ale zahrnují oboru celého řešení. Poskytují způsob, jak nastavit informace o autorovi, nastavení, kód formátování styly a správa verzí sestavení a umožňují pro způsob, jak přiřadit spouštěný projekt v řešení.  Dialogové okno Možnosti řešení je přístupná z **Projekt > Možnosti řešení** položky nabídky z **možnosti** položky kontextové nabídky na řešení v panelu pro řešení, nebo dvojím kliknutím na Řešení v panelu pro řešení:

 ![Možnosti řešení](media/projects-and-solutions-image7.png)
