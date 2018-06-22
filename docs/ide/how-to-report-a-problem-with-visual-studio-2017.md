---
title: Postup nahlásit problém s Visual Studio 2017
description: Zjistěte, jak chcete-li nahlásit problém s Visual Studio 2017 společnosti Microsoft, takže jsme diagnostikovat a opravit.
ms.custom: ''
ms.date: 03/11/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: bee01179-cde5-4419-9095-190ee0ba5902
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 735f0d5160466c81560ba5afb6bfc0e696d88230
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302923"
---
# <a name="how-to-report-a-problem-with-visual-studio-2017"></a>Postup nahlásit problém s Visual Studio 2017

Pokud dojde k potížím s Visual Studio, chceme vědět o něm. Zde je postup sestavy tyto potíže k [komunity vývojářů](https://developercommunity.visualstudio.com/) tak, aby jsme diagnostikovat a opravit.

## <a name="report-a-problem-by-using-visual-studio"></a>Nahlásit problém pomocí sady Visual Studio

Chcete-li nahlásit problém pro sadu Visual Studio, je nutné inicializovat sestavu ze sady Visual Studio nebo Visual Studio Instalační služby. Nelze provést přímo pomocí [komunity vývojářů](https://developercommunity.visualstudio.com/) webu. Vytváření sestav pomocí sady Visual Studio umožňuje diagnostické informace, které mají být automaticky zahrnuty v sestavě.

![Sestavy problém automaticky otevírané okno komunity vývojářů Visual Studio](media/report-an-issue.png)

1. V sadě Visual Studio, vyberte **pomoci** > **odeslat zpětnou vazbu** > **nahlásit problém**.

   > [!TIP]
   > Pokud nemůžete dokončit instalaci sady Visual Studio nebo nelze využít nástroj zpětné vazby v sadě Visual Studio, můžete nahlásit problém pomocí **instalační program Visual Studio**. To pokud chcete udělat, zvolte ikonu zpětné vazby v pravém horním rohu **instalační program Visual Studio**.

1. Pokud nejste přihlášení, vyberte **přihlásit**; je na pravé straně nástroje, jak je znázorněno na následujícím snímku obrazovky. Postupujte podle pokynů na obrazovce přihlášení.

   ![Přihlaste se k nahlásit problém](../ide/media/sign-in-new-ux.png)

   Při přihlášení, můžete na něm ohlásit problém, který se má, nebo hlasovat nebo nastavte jako komentář. Můžete také hlasovat nebo publikované na jiný problém, který se zobrazí komentář.

1. Visual Studio poskytuje rozhraní vyhledávání pro váš problém a zobrazit, pokud ostatní nahlásilo, příliš. Pokud někdo ohlásil ho, "až hlas" jej a dejte nám vědět.

   ![Hledání a hlasů pro podobné problémy](../ide/media/search-and-vote.png)

1. Pokud jste zjistil problém nenajdete, zvolte **problém nové sestavy** v dolní části obrazovky.

   > [!NOTE]
   > **Problém nové sestavy** tlačítko se zobrazí jenom v sadě Visual Studio rozhraní pro komunity vývojářů. Nelze nahlásit problém přímo na [komunity vývojářů](https://developercommunity.visualstudio.com/) webu.

1. Vytvořte popisný název pro problém, který pomáhá nám směrovat na správný tým Visual Studio.

1. Pokud je to možné, uveďte další podrobnosti a připojte postup, abychom mohli problém reprodukovat.

   ![Nahlásit problém nové](../ide/media/report-new-problem.png)

1. Vyberte **Další** přesunout do **přílohy** kartě. Zde můžete zaznamenat vaše aktuální obrazovku k odeslání společnosti Microsoft. Chcete-li připojit další snímky obrazovky nebo jiné soubory, zvolte **připojit další soubory**.

   ![Připojte snímek sestavy problém Visual Studio](media/report-a-problem-screenshot.png)

1. Pokud nechcete připojit snímek nebo [záznam zkopírujte](#record-a-repro), vyberte **Další** přesunout do **Souhrn** kartě.

1. Vyberte **odeslání** k odeslání zprávy, spolu s všechny Image a trasování nebo odkládacích souborů. (Pokud **odeslání** tlačítko je zobrazeno šedě, ujistěte se, že jste zadali název a popis pro sestavu.)

## <a name="record-a-repro"></a>Záznam zkopírujte

Trasování a haldy souborů výpisu paměti jsou užitečné v pomáhá nám diagnostikovat problémy. Vážíme si ho při použití **nahlásit problém** nástroj zaznamenávat vaše zkopírujte kroky a posílat data do Microsoftu. Chcete-li tak učinit:

1. Když zadáte název a popis pro váš problém, vyberte **Další** přesunout do **přílohy** kartě.

1. Vyberte **záznam** kartě.

1. V části **záznam vaše akce**, vyberte aktuální instance sady Visual Studio, pokud lze reprodukování problému došlo. Pokud není možné, například pokud je přestala Visual Studio, vyberte  **\<vytvoření nové instance >** k zaznamenání akce v nové instanci sady Visual Studio.

1. Vyberte **spustit záznam**. Udělte oprávnění ke spuštění nástroje.

   ![Zvolte "Spustit záznam" můžete zadat souboru výpisu trasování a haldy v sestavě problém Visual Studio](../ide/media/record-dialog-box.png)

1. Když **kroky zapisovač** nástroj se zobrazí, proveďte kroky, které problém reprodukovat.

1. Až budete hotoví, vyberte **zastavit záznam** tlačítko.

1. Počkejte několik minut pro sadu Visual Studio a shromažďovat informace, které jste si poznamenali balíčku.

## <a name="search-for-solutions-or-provide-feedback"></a>Hledání řešení nebo poskytnutí zpětné vazby

Pokud nechcete nebo nemůže používat Visual Studio k nahlásit problém, je šance, že problém již oznámen a řešení odeslány na [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/) stránky.

Pokud nemáte problém do sestavy, ale chcete poskytnout zpětnou vazbu produktu nebo návrh, je místo, takže příliš. Další informace najdete v tématu [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-ide) stránky.

## <a name="see-also"></a>Viz také:

* [Kontaktujte nás](../ide/talk-to-us.md)
* [Nahlásit problém pomocí sady Visual Studio pro Mac](/visualstudio/mac/report-a-problem)
* [Nahlásit problém s C++](/cpp/how-to-report-a-problem-with-the-visual-cpp-toolset)
* [Komunity vývojářů v sadě Visual Studio](https://developercommunity.visualstudio.com/)
* [Ochrana dat komunity vývojářů](developer-community-privacy.md)