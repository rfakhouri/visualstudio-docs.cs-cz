---
title: "Správa oprávnění správce na portálu správce předplatných sady Visual Studio"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 1/19/2018
Ms.topic: Get-Started-Article
Description: Learn how manage admins & super admins in the Visual Studio Subscriptions Administrator Portal.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 83bf27d5aaa99c2095ad8a1fafd7541df90f316b
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="managing-administrator-rights-in-the-visual-studio-subscriptions-administrator-portal"></a>Správa oprávnění správce na portálu správce předplatných sady Visual Studio

## <a name="overview"></a>Přehled 
V aplikaci Visual Studio odběry portálu správce (https://manage.visualstudio.com) existují dvě role správy:

**Super Admins:** při prvním nastavení organizace, bude primární server nebo obraťte se na oznámení super admin ve výchozím nastavení. Kontakt primární nebo oznámení můžete přiřadit další super admins nebo administrators. Kromě správy předplatného u jednotlivých odběratelů, super správce můžete přidávat a odebírat Další správci a správci superuživatele. Pokud v systému existuje více než dva super admins, super admin odstranit všechny kromě poslední dva pro zabezpečení. 

**Správci:** může správce spravovat Odběratelé, kteří ve smlouvách, které přiřadí super admin k nim.  Jejich můžete přiřadit odběry jednotlivcům, upravit odběry a přiřadit nebo je odeberte.   (Správci jsou jmenovaný Super Admins.)  

## <a name="adding-an-administrator-with-super-admin-rights"></a>Přidání správce **s** Super Admin práva:

1. Přihlaste se k Visual Studio odběry [portálu správce](https://manage.visualstudio.com) pomocí účtu, který již má oprávnění supersprávce.

2. Klikněte na **spravovat správci** v horní části stránky. (Pouze Super Správci mají přístup k na této kartě.  Správci, bez použití oprávnění supersprávce **spravovat odběratele** karta pro správu jednotlivých odběratelů.)

3. Klikněte na tlačítko **přidat** k vytvoření nového správce. 

4. Zadejte všechny požadované podrobnosti v místním okně Přidat správce.
  - Pokud vaše organizace má už zaregistrované v Azure Active Directory (AAD), začněte psát název v **název** pole a vyberte správné položky v rozevíracím seznamu. S novým uživatelům, zadejte úplný název a Ignorovat *žádné identity nalezen* oznámení.
  - Jakmile byl identifikován správný uživatele, bude automaticky vyplňovat pole přihlášení e-mailovou adresu. Zadejte e-mailovou adresu nového správce, pokud ještě není zadaná.

5. Vyberte **kontrolního čísla výrobku** chcete nový správce chcete spravovat, klikněte na rozevírací seznam v části **smlouvy**. Pokud kontrolního čísla výrobku jsou registrace má více než jednu smlouvu v něm, může správce poskytnout přístup k libovolné či ke všem smlouvy. 

**Další informace o smlouvy:** funkci rozevírací seznam v rámci smlouvy je zakázáno, je-li k dispozici pouze jednu smlouvu.  Když uživatele, kterého konfigurujete jsou udělena práva Super Admin, jsou automaticky zkontrolovány všechny smlouvy.

6. Klikněte **Super Admin** políčka umožníte práva superuživatele správce pro tohoto správce.  

7. Chcete-li dokončit přidání tohoto správce, klikněte na tlačítko **přidat**.

**Potenciální chybě při přidávání Admins:** některým uživatelům může zobrazit chybová zpráva při pokusu o přidání správce. Toto je může dojít, pokud super admin e-mailovou adresu, který je přidáván není uveden ve společnosti AAD. Chcete-li dokončit přidání nového správce, jednoduše chybu ignorovat a klikněte na **přidat** znovu. 

8. Po vytvoření superuživatele správce se zobrazí v seznamu správců a svého účtu, budou označeny zelená značka zaškrtnutí označující jejich stav supersprávce. 

### <a name="optional--add-a-different-notification-email"></a>Volitelné: Přidejte jiný oznamovací e-mail.
Pokud vaše organizace má jinou adresu nebo účet pro příjem e-maily, nyní máte možnost zadat adresu "Komunikace". Vyberte **přidat jiné oznamovací e-mail pro příjem komunikace**. 

*Příklad:* používá žádost rene@contoso.com když mu přihlásí pomocí pověření své společnosti.  Ale na žádost společnosti pouze používá tuto adresu ke správě přístupu k adresáři.  Při odesílání a přijímání e-mailů, žádost používá rene.collado@contoso.com, takže jeho Super Admin zadá adresu druhý zajistit dostane úvodní odešle poštu.  Pokud vaše společnost není nakonfigurována tímto způsobem, stačí zadat e-mailovou adresu přihlášení by mělo být dostatečné.

## <a name="adding-an-administrator-without-super-admin-rights"></a>Přidání správce **bez** Super Admin práva:

Stejný postup popsaný výše vhodné dodržovat Chcete-li přidat správci, bez oprávnění správce Super, ale vezme v úvahu následující aspekty:
-  Při přidávání správci bez oprávnění správce Super, není nutné pro další e-mailovou adresu, který se má přidat a políčka Super Admin zůstává prázdné.
-  Uživatelé bez oprávnění správce Super neobdrží zkontrolujte zelená ikona v jeho položku konfigurace profilu v části "Administrators spravovat".
