---
title: Visual Studio cloudové předplatné nákupu pro poskytovatele cloudových služeb
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 03/15/2018
ms.topic: Get-Started-Article
description: Informace pro poskytovatele cloudových řešení, o tom, jak zakoupit a spravovat odběry cloudových Visual Studio pro vaše zákazníky.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: bdf956b02c4bfc5125b452b6eece0cb39e454bc3
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36283374"
---
# <a name="buy-and-manage-visual-studio-cloud-subscriptions-for-your-customers"></a>Zakoupit a spravovat odběry cloudových Visual Studio pro vaše zákazníky

Partnerům v [Cloud Solution Provider (CSP)](https://partner.microsoft.com/en-US/cloud-solution-provider) programu můžete zakoupit Visual Studio Enterprise a Visual Studio Professional Cloudová předplatná, která pro své zákazníky.

[Porovnejte možnosti odběru cloudu](https://visualstudio.microsoft.com/vs/pricing)

## <a name="prerequisites"></a>Požadavky
Musíte nejprve nastavení klientů zákazníka v centru partnera a předplatné Azure, vytvořte pro tohoto klienta.
[Víc se uč](https://docs.microsoft.com/vsts/billing/csp/set-up-csp-customer)

## <a name="how-to-buy"></a>Jak koupit

<iframe src="//channel9.msdn.com/Shows/Visual-Studio-for-CSP-Partners/CSP-How-to-buy-Visual-Studio-Subscriptions/player" width="600" height="315" allowFullScreen="true" frameBorder="0"></iframe>

0. Přihlaste se [Partnerské centrum Microsoftu](https://partnercenter.microsoft.com).
0. Zvolte **zákazníci** a vyberte zákazníka kupovat.
0. Zvolte **Správa služeb**.
0. Zvolte **sady Visual Studio Marketplace**.
0. Ověřte, že je máte, název zákazníka je v pravém horním rohu.
0. Zvolte **odběry**.
0. Zvolte Enterprise nebo Professional a zvolte měsíční nebo roční pro sadu Visual Studio.
0. Zvolte **koupit**.
0. Zvolte předplatné Azure k vyúčtování pro nákup.
0. Zadejte počet uživatelů, které zákazník potřebuje.
0. Zkontrolujte pořadí a **potvrdit** ho.

>[!NOTE]
> Musíte provést následující kroky pokaždé, když zakoupit předplatné sady Visual Studio jako zprostředkovatel kryptografických služeb. V tuto chvíli není k dispozici žádné rozhraní API pro automatizaci nákupu.

Jakmile potvrdíte, nákup, můžete zvolit **spravovat** přiřadit předplatná zákazníka koncovým uživatelům.  Portálu pro správu předplatného můžete taky přistupovat ze Partnerské centrum tak, že zvolíte **Správa služeb**.  Zde najdete kroky nebo video níže.

## <a name="how-to-manage-visual-studio-cloud-subscriptions-for-your-customer"></a>Jak spravovat sady Visual Studio Cloudová předplatná vašeho zákazníka.

<iframe src="//channel9.msdn.com/Shows/Visual-Studio-for-CSP-Partners/CSP-How-to-manage-Visual-Studio-Subscriptions/player" width="600" height="315" allowFullScreen="true" frameBorder="0"></iframe>

0. Přihlaste se k [Partnerské centrum Microsoftu](https://partnercenter.microsoft.com).
0. Zvolte **zákazníci** a název zákazníka.
0. Zvolte **Správa služeb**.
0. Zvolte **Spravovat odběry sady Visual Studio**.

Pokud máte více než jedno předplatné pro tohoto zákazníka, pomocí rozevírací nabídky vyberte předplatné Azure, pomocí kterého jste provedli nákupu.  **Licence Souhrn** uvádí počet odběrů, které byly přiřazeny a jaká je dostupná pro jednotlivé možnosti cloudové předplatné sady Visual Studio.  Souhrn také umožňuje zakoupit další předplatné nebo snižte počet odběrů.

Zvolte **přidat** přiřadit předplatné s novým uživatelem.  Počet zobrazených aktualizace a koncový uživatel obdrží e-mailové oznámení.
Koncový uživatel může pak se přihlaste pomocí e-mailovou adresu, které jste zadali k aktivaci jeho předplatnému Visual Studio [portál odběratele Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs).

K přiřazení předplatné sady Visual Studio jiného uživatele, můžete odstranit aktuální odběratele a přidat nové odběratele.

Pokud odběratel ještě aktivována svoje předplatné sady Visual Studio, může to být vzhledem k tomu, že se e-mailová pozvánka vynechán.  Můžete požádat, že jsme znovu odeslat pozvánky aktivace uživateli z portálu pro správu sady Visual Studio příliš.

## <a name="view-visual-studio-pricing-for-csp-partners"></a>Zobrazení v sadě Visual Studio cenách pro partnery zprostředkovatele kryptografických služeb

Pokud chcete zobrazit sady Visual Studio cenách pro partnery CSP, přihlaste se k [Partnerské centrum](https://partnercenter.microsoft.com).  Zvolte **– ceny a nabízí** z levé NAV  Vyberte aktuálního měsíce ceny souboru pod **služeb na základě využití** v pravém horním rohu. Po stažení tabulky aplikace Excel, přejděte do **Azure ceník** list a filtrování **měření kategorie** sloupec, který se **Visual Studio**.

Zde je postup interpretovat zobrazené na této tabulky:
| Kategorie měření    |   Název                 |  Jednotky                                |           Toto je                          |
|-------------------|------------------------|---------------------------------------|-------------------------------------------------|
| Visual Studio     | Enterprise             |  Předplatné                         | Visual Studio Enterprise měsíční předplatné   |
| Visual Studio     | Enterprise (roční)    |  Roční předplatná                 | Visual Studio Enterprise roční předplatné    |
| Visual Studio     | Professional           |  Předplatné                         | Visual Studio Professional měsíční předplatné |
| Visual Studio     | Professional (roční)  |  Roční předplatná                 | Visual Studio Professional roční předplatné  |

Nabízíme slevu 5 % 6. jednotce, které můžete zakoupit (pro danou zákazníka) každý měsíc každé předplatné sady Visual Studio. Proto se zobrazí dva řádky pro jednotlivé možnosti odběru. Jeden řádek ukazuje "Minimální hodnotu" 0, který by měl interpretovat jako základní ceny pro jednotky 1 až 5. Druhý řádek ukazuje "Minimální hodnotu" 5, takže bude 5 % sleva, která se vztahuje na jednotky 6 a vyšší.


## <a name="frequently-asked-questions"></a>Nejčastější dotazy
### <a name="q-how-are-monthly-cloud-subscription-charges-processed"></a>Otázka: jak jsou **měsíční** cloudové předplatné poplatky zpracovat?
Odpověď: na první nákup vám účtujeme poměrné množství tak, aby pokrývalo zbývající počet dnů do aktuálního měsíce. Například pokud zakoupení 10 Cloudová předplatná měsíční Visual Studio Professional byl proveden v dubnu 15, pak jsme se účtují 5 jednotky, protože nejsou k dispozici left 15 dní v měsíci 30 dnů nebo 50 % a nám prorate jednotky poplatky z 50 %.
Na první může a každý měsíc po tomto datu až do zrušení, úplné 10 jednotek bude účtován.

Pokud zvýšíte množství placené později, prorate jsme vyšší jednotky tak, aby pokrývalo zbývající počet dnů do aktuálního měsíce. Pokud jste si zakoupili 1 Další Visual Studio Professional měsíční cloudové předplatné na může 10, vám proto by účtujeme zhruba 0.677 jednotky (21 dnů zbývajících do 31 den měsíce může).

### <a name="q-how-are-annual-cloud-subscription-charges-processed"></a>Otázka: jak jsou **roční** cloudové předplatné poplatky zpracovat?
Odpověď: při každém nákupu vám účtujeme celé množství zakoupili okamžitě. Poplatky za nejsou rozloženy v roce a neexistuje žádný k dispozici průběžné hodnoty. Pokud si zakoupíte roční předplatná cloudu v různých časech v roce, budete mít odběry obnovení v různých měsíců. Jsme neprovádějte všechny roční předplatná cloudu zákazníka shodných, jako je běžné s Microsoft svazek licencování smlouvy nákupu.

### <a name="q-how-do-cancelations-work"></a>Otázka: jak stornování funguje?
Odpověď: Při zrušení cloudové předplatné sady Visual Studio, jsou Zrušení automatického obnovení. Předplatné pokračuje v až do jeho normální obnovení data a pak jednoduše vyprší.
Na vypršení platnosti předplatitele sady Visual Studio už pomocí sady Visual Studio nebo jiné výhody z předplatného.

S měsíční Cloudová předplatná stornování projeví první den v měsíci Další. Pokud zrušíte jenom některé z vašich zákazníků měsíční Cloudová předplatná, nezapomeňte odebrat uživatele v prvním měsíci další zajistit, že oprávnění uživatelé dál obsahovat aktivní odběry, které jsou přiřazeny.

Roční předplatná cloudu stornování projeví první den měsíce následujícího po dobu 12 měsíců od data původního nákupu nebo se účtují 12 měsíců od poslední roční obnovení. Například pokud jste si zakoupili roční cloudové předplatné sady Visual Studio Enterprise na 3 leden 2018 pak zůstane aktivní až 1 února 2019 když ho automaticky obnovuje pro další rok. Pokud zrušíte kdykoli mezi potom a 1. února 2020 předplatné vyprší na 1. února 2020. Neexistuje žádné slevy pro zrušení součást způsobem až do roku předplatné s roční předplatná cloudu.

### <a name="q-what-kind-of-volume-discounts-are-available-for-visual-studio-subscriptions"></a>Otázka: jaký druh slevy jsou k dispozici pro Visual Studio předplatné?

Odpověď: můžete získat tak slevu 5 % 6. a všechny odběry ve *jednotlivých typů* předplatného:

* Visual Studio Professional každý měsíc
* Visual Studio Professional roční
* Visual Studio Enterprise každý měsíc
* Visual Studio Enterprise roční

Ano například pokud si zakoupíte 6 Visual Studio Professional měsíční odběry a 5 Visual Studio Enterprise měsíční předplatné, můžete budete platit regulární cenu na 5 Professional, rychle slevu 5 % 6. Professional a platit regulární cenu na všechny 5 Enterprise odběry.

Navíc slevy platí jenom pro poplatky v daném měsíční fakturační období. Proto pokud koupit 5 Visual Studio Professional roční předplatná za jeden měsíc, a potom si zakoupíte 5 Další dalšího měsíce, budete platit běžná cena na všechny odběry 10.

Tyto slevy se projeví v cenové dat v rámci [Partnerské centrum](https://partnercenter.microsoft.com).

### <a name="q-are-there-renewal-discounts"></a>Otázka: existují slevy obnovení?

Odpověď: Ne, ceny pro předplatné sady Visual Studio jsou ploché. Pro nové předplatné a trvalého předplatných se nabízí za stejnou cenu.

### <a name="q-are-there-azure-devtest-pricing-options-for-csps"></a>Otázka: existují Azure pro vývoj/testování ceny možnosti pro poskytovatele cloudových služeb?

Odpověď: není v tuto chvíli. Vaši zákazníci mohou využít výhod [ceny Azure pro vývoj/testování](http://aka.ms/azuredevtestpricing), ale nemáme nic speciálně pro CSP.