---
title: Osobní e-mailů, zobrazí na webu VLSC
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/23/2018
ms.topic: conceptual
description: Předplatná sady Visual Studio – proč vidím Hotmailu nebo Gmailu adresy pro moje předplatitele?
ms.openlocfilehash: 3f546151beba8ac360c0ad7db3154ea836942798
ms.sourcegitcommit: 208395bc122f8d3dae3f5e5960c42981cc368310
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/10/2019
ms.locfileid: "67784455"
---
# <a name="visual-studio-subscriptions--why-am-i-seeing-hotmail-or-gmail-addresses-for-my-subscribers"></a>Předplatná sady Visual Studio – proč vidím Hotmailu nebo Gmailu adresy pro moje předplatitele?

Společností z na svazek licencování Service Center (VLSC) migraci na novou sadu Visual Studio [portál pro správu předplatných](https://manage.visualstudio.com), Správce může překvapeni, pokud chcete zjistit, který "Přihlášení e-mailovou adresu" pro některé předplatitele ukazuje 3. stran e-mailovou adresu jako Hotmail, Gmail nebo Yahoo.  Další informace, podívejte se na [toto video](https://www.youtube.com/watch?v=1op-i1zEMfY&t=0s&list=PLReL099Y5nRfDyvvwzNDBaZe7qTxmuM2T&index=6).

## <a name="cause"></a>Příčina

K této situaci dochází z důvodu přihlášení procesy, které byly přidruženy k starší verze prostředí pro předplatitele MSDN. Uživatelé se migrovaly ze svazku licence Service Center (VLSC) na nový portál bez úprav. Správci nemusí být vědomi, že uživatelé používala osobní účty pro přístup k svých předplatitelských výhod. Před migrací předplatitele sady Visual Studio, které byly dokončeny v 2016, byly dvě akce potřebné pro úspěšné fungování předplatné sady Visual Studio:
1. Správce "přiřazeno" předplatné jednotlivých odběratele, pomocí jejich pracovních nebo školní e-mailovou adresu.
2. Odběratel "" předplatné aktivovali.

Během procesu aktivace předplatitele: Účet Microsoft (MSA) byla nutná k registraci. Při pokusu o jejich pracovní nebo školní účet nebyl v odběrateli (třeba tasha@contoso.com) s MSA, může vytvořit nové MSA nebo využít některý z existujících. Kvůli tomu "Sign in e-mailovými adresami" se liší od jejich "přiřazené k e-mailovou adresu".

> [!NOTE]
> Nové prostředí odběratele na [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs) podporuje typy identity pracovní/školní a účet Microsoft (má).

Nakonec od správce migrace trvá data z webu VLSC týkající odběratele "Sign In e-mailovou adresu" k naplnění nové prostředí pro správu odběratele, nedávno migrované správci může zobrazit tyto dříve bez povšimnutí osobní účty z důvodu změny v uživatelském rozhraní, které zviditelnit tyto informace.

## <a name="solution"></a>Řešení

Chcete-li tento problém, budete muset upravit informace o odběrateli aktualizovat jeho přihlašovací e-mailové adresy.  Úpravy můžete provést u jednotlivých odběratelů nebo hromadně. Podrobnější informace, navštivte prosím [úprava předplatného](edit-license.md).

Po aktualizaci předplatitelů e-mailové adresy, můžete chtít upozornit, že došlo ke změně jejich přihlašovací údaje.  Také obdrží e-mail s aktualizované informace.