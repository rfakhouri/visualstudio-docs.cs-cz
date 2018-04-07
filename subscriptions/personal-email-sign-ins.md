---
title: Osobní E-maily, které se zobrazí v VLSC
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/23/2018
ms.topic: Get-Started-Article
description: Visual Studio odběry – Proč se zobrazuje Hotmail nebo z Gmailu adresy pro moje odběratele?
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: cfe035d82976e3df683f4e3a35bd9d7f3c8cf9e2
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2018
---
# <a name="visual-studio-subscriptions--why-am-i-seeing-hotmail-or-gmail-addresses-for-my-subscribers"></a>Visual Studio odběry – Proč se zobrazuje Hotmail nebo z Gmailu adres pro moje odběratele? 

Jako společností migrovat z webu Volume Licensing Service Center (VLSC) do nové sady Visual Studio [portálu pro správu předplatných](https://manage.visualstudio.com), Správce může být Překvapený najít, "Přihlášení e-mailovou adresu" pro některé odběratele Zobrazuje 3. stran e-mailovou adresu jako Hotmail, z Gmailu nebo Yahoo.

## <a name="cause"></a>příčina

K této situaci dojde kvůli přihlášení procesy, které byly přidruženy starší verze msDN odběratele prostředí. Uživatelé byly migrovány z webu VLSC do nového portálu bez úprav. Někteří správci pravděpodobně neví, že uživatelé používala osobní účty pro přístup k jejich odběru výhody. Před migrací odběratele Visual Studio, které byly dokončeny v 2016, byly dvě akce požadované úspěšně použití odběru Visual Studio:
1. Správce "přiřazené" předplatné jednotlivých odběratele, pomocí svého pracovního nebo školního e-mailovou adresu.
2. Odběratel "aktivovat" předplatné.

Během procesu aktivace odběratele: A účet Microsoft (msA) vyžaduje přihlášení. Pokud odběratel nebyla pokus o jejich pracovní nebo školní účet (například John@contoso.com) na účet spravované služby, můžou vytvořit nový účet spravované služby nebo využívat stávající. Výsledkem jejich "přihlášení e-mailovou adresu" se liší od jejich "přiřazené k e-mailová adresa".

> [!NOTE] 
> Nové prostředí odběratele na [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs) podporuje pracovní nebo školní a typů identit Microsoft Account (msA).

Vzhledem k tomu, že Správce migrace trvá data z webu VLSC týkající se odběratele "přihlášení e-mailovou adresu" k naplnění nové prostředí pro správu odběratele, nakonec může nedávno migrované správci uvidí tyto dříve bez povšimnutí osobní účty z důvodu změny do uživatelského rozhraní, které zviditelnit tyto informace.

## <a name="solution"></a>Řešení

K odstranění problému, budete muset upravit informace o odběru k aktualizaci jejich přihlášení e-mailové adresy.  Můžete provedeny úpravy, u jednotlivých odběratelů nebo hromadně. Úplné informace, navštivte [úpravou odběru](/visualstudio/subscriptions/edit-license).  

Jakmile jste aktualizovali subscriber(s) e-mailové adresy, můžete s upozorněním, že došlo ke změně jejich přihlašovací údaje.  