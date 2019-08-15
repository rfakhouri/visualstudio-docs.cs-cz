---
title: Osobní e-maily zobrazené v VLSC
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/24/2019
ms.topic: conceptual
description: Předplatná sady Visual Studio – proč se mi zobrazují adresy služby Hotmail nebo Gmail pro moje předplatitele?
ms.openlocfilehash: 8418a177e793f0b4fe9a5019d2cf62fa724312ff
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605754"
---
# <a name="visual-studio-subscriptions--why-am-i-seeing-hotmail-or-gmail-addresses-for-my-subscribers"></a>Předplatná sady Visual Studio – proč se mi zobrazují adresy služby Hotmail nebo Gmail pro moje předplatitele?
Po migraci společností z webu Volume Licensing Service Center (VLSC) na nový [portál pro správu](https://manage.visualstudio.com)předplatných sady Visual Studio byli správci překvapeni, že přihlašovací e-mailová adresa pro některé předplatitele zobrazuje e-mail třetí strany. adresa jako Hotmail, Gmail nebo Yahoo.  Další informace najdete v [tomto videu](https://www.youtube.com/watch?v=J61EYaVN-dQ&list=PLReL099Y5nReJhZ6o8CQFPSBgzGCHX99_&index=6).

## <a name="cause"></a>příčina
K tomuto scénáři dochází v důsledku procesů přihlašování, které byly přidruženy k starší verzi služby předplatitele MSDN. Uživatelé byli migrováni z webu Volume License Service Center (VLSC) na portál pro správu předplatných sady Visual Studio bez úprav. Správci možná nebudou vědomi, že uživatelé používali osobní účty pro přístup k výhodám jejich předplatného. Před migrací předplatitele sady Visual Studio, které byly dokončeny v 2016, byly pro úspěšné použití Visual Studio Subscription nutné dvě akce:
1. Správce přiřadil předplatné individuálnímu předplatiteli pomocí své pracovní nebo školní e-mailové adresy.
2. Předplatné je aktivované předplatitelem.

Během procesu aktivace předplatitele: Pro přihlášení se vyžaduje účet Microsoft (MSA). Pokud se předplatitel nepokusí svůj pracovní nebo školní účet (např. tasha@contoso.com) MSA, mohl vytvořit nový MSA nebo využít stávající. Výsledkem je, že se "e-mailová adresa pro přihlášení" liší od jejich "přiřazeno e-mailové adresy".

> [!NOTE]
> Nové prostředí pro předplatitele [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) v systému podporuje typy identit pracovní/školní a účet Microsoft (MAA).

Vzhledem k tomu, že migrace správce přebírá data z VLSC týkající se přihlašovací e-mailové adresy odběratele, aby naplnila nové prostředí pro správu předplatitele, mohl by nedávno migrované správce vidět tyto dřív neuvedené osobní účty. z důvodu změn v uživatelském rozhraní, které tyto informace podrobněji vystavily.

## <a name="solution"></a>Řešení
Chcete-li tento problém vyřešit, budete muset upravit informace o odběrateli a aktualizovat e-mailové adresy pro přihlášení.  Úpravy mohou být provedeny pro jednotlivé předplatitele nebo hromadně. Úplné informace najdete v úpravách [Upravit předplatné](edit-license.md)

##  <a name="next-steps"></a>Další postup
- Pokud jste aktualizovali e-mailové adresy odběratelů, můžete jim sdělit, že se změnily přihlašovací údaje.  Budou také dostávat e-maily s aktualizovanými informacemi.
- Může být užitečné [filtrovat seznam předplatitelů](search-license.md) ve vaší organizaci, aby se hledaly e-mailové adresy, které může být potřeba změnit.  

