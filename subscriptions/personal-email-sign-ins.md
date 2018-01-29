---
title: "Osobní E-maily, které se zobrazí v VLSC"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 1/23/2018
Ms.topic: Get-Started-Article
Description: "Visual Studio Subscriptions – Why Am I Seeing Hotmail or Gmail Addresses for My Subscribers?"
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 2bfe2f39d432be5fc6ff7b24be2a218d02fce961
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="visual-studio-subscriptions--why-am-i-seeing-hotmail-or-gmail-addresses-for-my-subscribers"></a>Visual Studio odběry – Proč se zobrazuje Hotmail nebo z Gmailu adresy pro moje odběratele? 

Jako společností migrovat z webu Volume Licensing Service Center (VLSC) do nové sady Visual Studio [portálu pro správu předplatných](https://manage.visualstudio.com), Správce může být Překvapený najít, "Přihlášení e-mailovou adresu" pro některé odběratele Zobrazuje 3. stran e-mailovou adresu jako Hotmail, z Gmailu nebo Yahoo.

## <a name="cause"></a>příčina

K této situaci dojde kvůli přihlášení procesy, které byly přidruženy starší verzi prostředí odběratel MSDN. Uživatelé byly migrovány z webu VLSC do nového portálu bez úprav. Někteří správci pravděpodobně neví, že uživatelé používala osobní účty pro přístup k jejich odběru výhody. Před migrací odběratele Visual Studio, které byly dokončeny v 2016, byly dvě akce požadované úspěšně použití odběru Visual Studio:
1. Správce "přiřazené" předplatné jednotlivých odběratele, pomocí svého pracovního nebo školního e-mailovou adresu.
2. Odběratel "aktivovat" předplatné.

Během procesu aktivace odběratele:
1. Microsoft účtu (MSA) se vyžaduje k přihlášení.
2. Pokud odběratel nebyla pokus o jejich pracovní nebo školní účet (například John@contoso.com) na účet spravované služby, můžou vytvořit nový účet spravované služby nebo využívat stávající.
3. Výsledkem jejich "přihlášení e-mailovou adresu" se liší od jejich "přiřazené k e-mailová adresa".

> [!NOTE] 
> Nové prostředí odběratele na [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) podporuje typy identity pracovní nebo školní a účet Microsoft (MSA).

Vzhledem k tomu, že Správce migrace trvá data z webu VLSC týkající se odběratele "přihlášení e-mailovou adresu" k naplnění nové prostředí pro správu odběratele, nakonec může nedávno migrované správci uvidí tyto dříve bez povšimnutí osobní účty z důvodu změny do uživatelského rozhraní, které zviditelnit tyto informace.

## <a name="solution"></a>Řešení

K odstranění problému, budete muset upravit informace o odběru k aktualizaci jejich přihlášení e-mailové adresy.  Můžete provedeny úpravy, u jednotlivých odběratelů nebo hromadně. Úplné informace, navštivte [úpravou odběru](/visualstudio/subscriptions/edit-license).  

Jakmile jste aktualizovali subscriber(s) e-mailové adresy, můžete s upozorněním, že došlo ke změně jejich přihlašovací údaje.  