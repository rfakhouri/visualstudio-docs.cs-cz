---
title: Nastavení předvoleb smlouvy na portálu pro správu
author: evanwindom
ms.author: lank
manager: lank
ms.date: 08/21/2019
ms.topic: conceptual
description: Přečtěte si, jak nastavit předvolby pro jazyky, kontakty, úroveň předplatného a další na portálu pro správu.
ms.openlocfilehash: 24e9ddfa92ee63e4d15eea086224e1069d4bcbc8
ms.sourcegitcommit: c90a998716b3dfa614dedc61a1bea515364efbec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/23/2019
ms.locfileid: "70001440"
---
# <a name="set-preferences-for-your-agreements-in-the-administration-portal"></a>Nastavení předvoleb pro vaše smlouvy na portálu pro správu
Super správci teď můžou nastavit určité Předvolby na portálu pro správu (portál pro správu), které se použijí globálně pro každou smlouvu.  Tyto preference určují, co můžou správci na vašich smlouvách nastavit, když přidávají předplatitelé, a můžou je jenom globálně upravovat jenom správci super.  

## <a name="access-preferences"></a>Předvolby přístupu
Abyste mohli zobrazit nebo upravit předvolby, musíte být přihlášeni k [portálu pro správu](https://manage.visualstudio.com) pomocí přihlašovacího ID, které má práva správce k této smlouvě.  

Nastavení předvoleb:
1. Přihlaste se k portálu pro správu s ID, které má oprávnění superuživatele.
2. Klikněte na kartu **Správa správců** .
   > [!div class="mx-imgBorder"]
   > ![Tlačítko Předvolby správce](_img/admin-prefs/admin-prefs-button.png)

3. Klikněte na **Předvolby smlouvy**.
Panel se otevře vpravo a zobrazí se vaše dostupné předvolby. 

   > [!div class="mx-imgBorder"]
   > ![Dialogová okna Předvolby pro správu](_img/admin-prefs/admin-prefs-flyout.png)

## <a name="set-your-preferences"></a>Nastavit předvolby
Pojďme prozkoumat všechny dostupné předvolby a jejich účinky. 

### <a name="agreement"></a>Ujednání
Pokud máte více smluv, pro které jste nadřízeného, budete moci zvolit požadovanou smlouvu v rozevíracím seznamu.  Předvolby, které nastavíte, se použijí jenom pro danou smlouvu.  Při přiřazování předplatných můžou jednotliví správci potlačit některé z těchto předvoleb na základě případu. 

Pokud je k e-mailové adrese, kterou jste použili k přihlášení, přidružená jenom jedna smlouva, zobrazí se a rozevírací seznam bude zakázaný. 

### <a name="contact-email-address"></a>Kontaktní e-mailová adresa
Tato předplatná nabízí způsob, jak můžou předplatitelé kontaktovat správce prostřednictvím tlačítka **kontaktujte správce** na [stránce Předplatná](https://my.visualstudio.com/subscriptions) na portálu pro předplatitele.  Pokud je tato předvolba prázdná, zprávy předplatitele se předají všem správcům a superuživatele v této smlouvě.  K přizpůsobení cílové skupiny pro tento kontaktní e-mail doporučujeme použít e-mailový alias skupiny nebo skupinu zabezpečení. Můžete také zvolit zadání e-mailové adresy jednotlivce, pokud dáváte přednost.

> [!NOTE]
> E-mailová adresa, kterou tady uvedete, se zákazníkům neposkytne.  Když předplatitel odešle na portál odběratele žádost o **kontakt my admin** , zpráva se přepošle na alias, aniž by ji vystavil předplatitelům. 

### <a name="default-external-subscribers-setting"></a>Nastavení výchozích externích odběratelů
Tato předvolba vám umožní rozhodnout, jestli správci můžou přidat předplatitele mimo tenanta nebo tenant vaší organizace.  Pokud tuto možnost vypnete, nepovolí se žádní externí předplatitelé.  Pokud ji povolíte a správce se pokusí přidat mimo předplatitele, zobrazí se jim výzva k potvrzení výběru a bude jim povoleno přiřadit předplatné. Správci nemohou přepsat toto nastavení. 

### <a name="default-downloads-setting"></a>Výchozí nastavení stahování
Povolení tohoto nastavení, které je ve výchozím nastavení zapnuté, umožní předplatitelům přístup ke stažení, když správci vytvoří nové předplatné.  Správci stále můžou zakázat stahování na základě jednotlivých předplatných.  

### <a name="default-subscription-level"></a>Výchozí úroveň předplatného
Pomocí tohoto nastavení můžete určit, která z úrovní předplatného zahrnutých ve vaší smlouvě je standardně vybraná, když se k uživateli přiřadí předplatné.  Správci můžou toto nastavení změnit na libovolnou úroveň předplatného ve vaší smlouvě – to stačí, když nebudete muset opakovaně dělat nejběžnější volbu. 

### <a name="default-communication-preferences"></a>Výchozí předvolby komunikace
Nastavení výchozího komunikačního jazyka a národního prostředí může zjednodušit proces přiřazování předplatných.  Pokud je váš vývojový tým založen například na jiné zemi, než je váš tým pro správu, můžete nastavit předvolby nejvhodnější pro umístění předplatitelů. Tato nastavení může i nadále měnit všichni správci pro jednotlivé předplatitele. 

## <a name="frequently-asked-questions"></a>Nejčastější dotazy
### <a name="q--can-i-disable-the-contact-email-address-so-subscribers-cannot-contact-administrators"></a>Č  Můžu zakázat **kontaktní e-mailovou adresu** , aby předplatitelé nemuseli kontaktovat správce?
O:  Ne. když se můžete rozhodnout, kteří správci budou kontaktováni pomocí skupiny zabezpečení, e-mailového aliasu nebo jednotlivé e-mailové adresy, funkci nejde zakázat.

### <a name="q-if-i-answer-a-subscribers-email-will-they-have-my-email-address"></a>Č Když odpovím e-mailem předplatitele, budou mít e-mailovou adresu?
O:  Vzhledem k tomu, že vaše odpověď přijde z libovolného e-mailového klienta, který používáte, zobrazí odpověď, kterou předplatitel obdrží, na základě e-mailové adresy, kterou používáte.  Pokud tedy budete reagovat z aliasu skupiny, uvidí se alias skupiny.  Pokud odpovíte z vlastní e-mailové adresy, uvidí to.  

### <a name="q-where-can-i-find-out-more-about-the-contact-my-admin-feature-in-the-subscriber-portal"></a>Č Kde se dozvím Další informace o funkci **kontakt my admin** na portálu pro předplatitele?
O:  Podívejte se na náš [Kontakt na můj správce](contact-my-admin.md) . 

### <a name="q-if-we-dont-complete-the-contact-email-address-and-a-subscriber-uses-the-contact-my-admin-feature-who-receives-their-request"></a>Č Pokud nedokončíte **kontaktní e-mailovou adresu** a předplatitel používá funkci **kontaktujte my admin** , která obdrží svoji žádost?
O:  Pokud v předvolbách **kontaktní e-mailová** adresa není nastavená žádná konkrétní e-mailová adresa, žádost obdrží všichni správci smlouvy. 

## <a name="resources"></a>Prostředky
- [Podpora správy a předplatných sady Visual Studio](https://visualstudio.microsoft.com/support/support-overview-vs)

## <a name="next-steps"></a>Další postup
- Informace o tom, jak [přiřadit odběry](assign-license.md)
- Další informace o plném rozsahu [výhod](https://visualstudio.microsoft.com/vs/benefits/) předplatného

