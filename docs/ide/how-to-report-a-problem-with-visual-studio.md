---
title: Postup ohlášení problému se sadou Visual Studio
description: Přečtěte si postup ohlášení problému se sadou Visual Studio
ms.date: 03/11/2018
ms.topic: conceptual
ms.assetid: bee01179-cde5-4419-9095-190ee0ba5902
ms.author: seiyer
author: seaniyer
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b130c321e57cdeea6b703b0e439d6b0f15a1a96
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "59232538"
---
# <a name="how-to-report-a-problem-with-visual-studio-or-visual-studio-installer"></a>Postup ohlášení problému se sadou Visual Studio nebo instalační program sady Visual Studio

> [!NOTE]
> Visual Studio pro Mac, najdete v části [jak chcete nahlásit problém v sadě Visual Studio pro Mac](/visualstudio/mac/report-a-problem).

Nahlásit problém z jeho instalačního programu nebo aplikace Visual Studio s použitím nástroje pro zpětnou vazbu v nich zahrnuty. Nástroje pro zpětnou vazbu umožňuje snadné zahrnutí diagnostických informací do vaší zpětné vazby a pomáhá diagnostikovat a opravovat problémy mnohem efektivněji v týmu sady Visual Studio. Tady jsou kroky, chcete nahlásit problém.

1. **V sadě Visual Studio**, vyberte ikonu zpětné vazby v pravém horním rohu a vyberte možnost nahlásit problém. Nástroje pro zpětnou vazbu se můžete dostat taky z nabídky **pomáhají** > **odeslat zpětnou vazbu** > **nahlásit problém**.
![Vytvoření sestavy automaticky otevírané okno problém komunity vývojářů v aplikaci Visual Studio](media/vsfeedbackentry.png) Alternativně nahlásit problém v **instalační program sady Visual Studio** Pokud nelze nainstalovat sadu Visual Studio nebo nemůžou využívat nástroj zpětné vazby v sadě Visual Studio .  V instalačním programu vyberte ikonu zpětné vazby v pravém horním rohu a vyberte nahlásit problém.
![Vytvoření sestavy automaticky otevírané okno problém komunity vývojářů v aplikaci Visual Studio](media/installer.png)

1. Pokud není přihlášení, vyberte **Sign In** jak je znázorněno na následujícím snímku obrazovky. Postupujte podle pokynů na obrazovce pro přihlášení.

   ![Přihlaste se k nahlášení problému](../ide/media/sign-in-new-ux.png)

   Nejenže můžete je ohlásit problém při přihlášení, ale také můžete hlasovat a komentáře k existující svůj názor.

1. Jakmile se přihlásíte, budete moci zobrazit vaše **problémy** a **aktivity** na **položky, které sleduji** obrazovky

   ![Položky, které sleduji](../ide/media/items-i-follow.png)

1. Visual Studio poskytuje rozhraní pro hledání na váš problém a zobrazit, pokud ostatní ho nahlásili. Pokud někdo ho ohlásil, "nahoru vote" jej a dejte nám vědět.
   > [!NOTE]
   > Pokud chcete hledat, zadejte požadovaný text do vyhledávacího pole a klikněte na tlačítko Enter nebo stiskněte ikonu hledání.

   ![Vyhledávání a můžete hlasovat pro podobné problémy](../ide/media/search-and-vote.png)

1. Pokud jste narazili na problém nenajdete, zvolte **ohlásit nový problém** v dolní části obrazovky.

   > [!NOTE]
   > **Ohlásit nový problém** tlačítko se zobrazí pouze v rozhraní sady Visual Studio pro komunity vývojářů. Nelze ohlásit problém přímo na [komunity vývojářů](https://developercommunity.visualstudio.com/) webu.

1. Vytvořte popisný název problému, který pomáhá nám směrovat správnému týmu sady Visual Studio.

1. Pokud je to možné, uveďte další podrobnosti a připojte postup, abychom mohli problém reprodukovat.

   ![Nahlášení nového problému](../ide/media/report-new-problem.png)

1. Vyberte **Další** přesunete **přílohy** kartu. Tady můžete zachytit aktuální obrazovce, která se odesílají je společnosti Microsoft. Chcete-li připojit další snímky obrazovky nebo jiné soubory, zvolte **připojit další soubory**.

   ![Snímek obrazovky připojení k hlášení o problému sady Visual Studio](media/report-a-problem-screenshot.png)

1. Pokud nechcete připojit snímek obrazovky nebo [zaznamenávat reprodukci](#record-a-repro)vyberte **Další** přesunout do **Souhrn** kartu.

1. Vyberte **odeslat** k odeslání zprávy, spolu s všechny Image a soubory trasování nebo s výpisem paměti. (Pokud **odeslat** tlačítko nejde aktivovat, ujistěte se, že jste zadali název a popis sestavy.)

   Informace o tom, jaká data se shromažďují, naleznete v tématu [Data shromažďujeme](developer-community-privacy.md#data-we-collect).

## <a name="record-a-repro"></a>Záznam reprodukci

Trasování a haldy soubory s výpisem paměti jsou užitečné při nám s diagnostikou problémů. Vážíme si ho použijete **nahlásit problém** nástroj pro záznam postupu k reprodukci a odesílala data do Microsoftu. Tady je postup:

1. Jakmile zadáte název a popis pro váš problém, vyberte **Další** přesunete **přílohy** kartu.

1. Vyberte **záznam** kartu.

1. V části **zaznamenejte své akce**, vyberte aktuální instanci aplikace Visual Studio, pokud dokážete existuje problém reprodukovat. Pokud není možné, například pokud je zablokování sady Visual Studio, vyberte  **\<vytvořit novou instanci >** pro záznam akce v nové instanci sady Visual Studio.

1. Vyberte **spustit záznam**. Udělit oprávnění ke spuštění nástroje.

   ![Zvolte možnost "Spustit záznam" Zadejte soubor s výpisem paměti trasování a haldy v hlášení o problému sady Visual Studio](../ide/media/record-dialog-box.png)

1. Když **záznam kroků** nástroje se zobrazí, proveďte kroky, které problém reprodukovat.

1. Jakmile budete hotovi, zvolte **zastavit záznam** tlačítko.

1. Počkejte několik minut, než Visual Studio se shromažďovat a balit informace, které jste si poznamenali.

   Informace o tom, jaká data se shromažďují, naleznete v tématu [Data shromažďujeme](developer-community-privacy.md#data-we-collect).

## <a name="when-further-information-is-needed-need-more-info"></a>Při další informace o nic (nutné další informace)

Od verze Visual Studio 2017 verze 15.5, je nový pracovní postup k poskytování pomoci uživatelům poskytovat další informace o zaslaných zprávách o.

1. Když se nastaví technický pracovník Microsoftu [komunity vývojářů v aplikaci Visual Studio](https://developercommunity.visualstudio.com/) problém na **nutné další informace** stavu, každý uživatel, který pošle, hlasovali, a potom nebo okomentováno problém obdrží oznámení ve **Nahlašování problémů A** nástroje v sadě Visual Studio.

   ![Potřebujete další informace o oznámení v sadě Visual Studio](../ide/media/nmi-notification.png)

1. Klikněte na **zobrazit problémy** odkaz k filtrování a řazení zobrazení problémů, které vyžadují pozornost. Tyto problémy je navíc indikátor vedle sebe, k rozlišení je obecně hledání.

1. Klikněte na problém, chcete-li zobrazit podrobnosti o tomto problému naleznete v tématu.

   ![Potřebujete další informace o oznámení](../ide/media/nmi-details-view.png)

1. Chcete-li zobrazit **nutné další informace** požádat, klikněte na tlačítko **zobrazit jejich žádost a Odpovědět** odkaz v zobrazení Podrobnosti o problému. Dialogové okno zobrazí požadavek.

   ![Potřebujete další informace o oznámení](../ide/media/nmi-request.png)

1. Další informace můžete zadat tak, že přidáte komentáře, přílohy nebo záznam kroků. Toto prostředí je podobný oznamování nového problému nebo poskytují dodatečné informace při hlasování o problém.

1. Žádost o technický pracovník Microsoftu obdrží oznámení o další informace k dispozici. Pokud mají dostatek informací k prošetření, změní se stav problému. V opačném případě inženýr vyzve k zadání i další informace.

   > [!NOTE]
   > * Při odesílání odpovědi, oznámení zmizí. Místo toho uvidíte banner, který vám a umožňuje poskytovat i další informace.
   > * Jakmile problém změní stav, oznámení zmizí pro všechny uživatele, který sleduje problém.
   > * Víc než jedna osoba může odpovědět na stejném **nutné další informace** požadavku.
   > * Není k dispozici **nutné další informace** pracovního postupu na [komunity vývojářů](https://developercommunity.visualstudio.com/) Pokud přistoupíte přímo přes webový prohlížeč, ale můžete také zadat komentáře a přílohy existuje.

## <a name="search-for-solutions-or-provide-feedback"></a>Vyhledejte řešení nebo poskytnout zpětnou vazbu

Pokud nechcete nebo nemůžete použít Visual Studio Pokud chcete nahlásit problém, je příležitost problém již oznámen a řešení, pošle [komunity vývojářů v aplikaci Visual Studio](https://developercommunity.visualstudio.com/) stránky.

Pokud nemáte problém nahlásit, ale chcete navrhnout funkci, je místo, kde, příliš. Další informace najdete v tématu [navrhnout funkci](https://developercommunity.visualstudio.com/content/idea/post.html?space=8) stránky.

## <a name="see-also"></a>Viz také:

* [Kontaktujte nás](../ide/talk-to-us.md)
* [Ohlášení problému se sadou Visual Studio pro Mac](/visualstudio/mac/report-a-problem)
* [Ohlášení problému se sadou C++](/cpp/how-to-report-a-problem-with-the-visual-cpp-toolset)
* [Visual Studio Developer Community](https://developercommunity.visualstudio.com/)
* [Ochrana dat pro vývojáře komunity](developer-community-privacy.md)
