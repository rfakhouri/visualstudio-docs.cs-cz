---
title: Časté otázky k migraci správce VLSC | Dokumentace Microsoftu
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 03/13/2018
ms.topic: conceptual
description: Časté otázky k migraci Volume License Service Center správce
searchscope: VS Subscription
ms.openlocfilehash: 43b5ff7aeddf5ba1d938709e9f395f50395d0f3d
ms.sourcegitcommit: 05d104a14ff357d599ff274f97cd59d464ee4a46
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2019
ms.locfileid: "58897657"
---
# <a name="visual-studio-subscriptions-administration-migration"></a>Migrace správy předplatných služby Visual Studio

V průběhu několika následujících měsíců se chystají změny sloužící ke správě předplatných sady Visual Studio (dříve předplatná MSDN). V současné době můžete koupit předplatná prostřednictvím multilicence a předplatná se spravují na portálu Volume License Service Center (VLSC) sady Visual Studio. Vytváří se nový portál pro správu a předplatných sady Visual Studio se budou spravovat na tomto novém portálu v budoucnu. Kromě existující operace poskytované na webu VLSC vám umožní na novém portálu hromadné přiřazení bez omezení, sledování a filtrování předplatných a možnost využívat Azure Active Directory (Azure AD) pro správu přístupu. Nový portál pro správu Visual Studio budou umístěné v: [ https://manage.visualstudio.com ](https://manage.visualstudio.com).

> [!Note]
> Tato migrace nebude mít vliv na MPSA zákazníky.

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

### <a name="why-is-it-changing"></a>Proč k této změně dochází?
Na novém portálu se optimalizovat prostředí správy předplatných sady Visual Studio a vytvoření jednotného prostředí pro správu předplatných sady Visual Studio, bez ohledu na to, jak byly zakoupeny. Nový portál má novou platformu, která umožňuje službě Azure AD a USA se umístí do budoucna. Kromě toho bude mít aktualizované uživatelské rozhraní, které se bude snadněji přejít a používat, zvyšuje efektivitu správců.

### <a name="who-will-be-impacted"></a>Kdo bude mít vliv?
Tato změna ovlivní všechny zákazníky, kteří mají aktivními multilicenčními smlouvami a zakoupili předplatných sady Visual Studio prostřednictvím multilicenčního programu.

### <a name="when-is-it-changing"></a>Pokud k této změně dochází?
To je obrovská přechod a dokončí se ve fázích, dokud na nový portál pro správu nebudou migrováni všichni zákazníci s aktivními multilicenčními smlouvami pro předplatná sady Visual Studio. Migrace se zahájila v prvním čtvrtletí 2017. Budeme informovat naše zákazníky s multilicenčními programy s předstihem plánovaný týden jejich migrace.

### <a name="does-my-organization-need-to-sign-up-for-azure-active-directory-azure-ad"></a>Potřebuje Moje organizace zaregistrovat do služby Azure Active Directory (Azure AD)?
Vaše organizace není nutné se zaregistrovat do služby Azure AD, ale můžete to provést kdykoli. Pokud budete chtít připojit ke službě Azure AD, můžete tak provést bez poplatků pomocí na úrovni free pro službu Azure AD. S Azure Active Directory budete s vyšší zabezpečení, řízení a dlouhodobou spolehlivost chránit organizaci. Nicméně pokud nejste připraveno pro Azure AD, se budete moci pokračovat v používání Accounts Microsoft (MSA) stejně jako dnes.

### <a name="how-do-i-know-when-my-organization-will-be-migrated"></a>Jak poznám, kdy se budou migrovat Moje organizace?
Primární nebo informační kontakt obdrží e-mail od nás vyzývající k dokončení procesu registrace jeden týden před migrací vaší organizace. Správci předplatného také obdrží e-mail s informacemi o tom, že jsme kontaktovali primární nebo informační kontakty a poskytuje podrobnosti o tom, jak zajistit úspěšnou registraci. Zjistěte, jak [vyhledejte vaší organizace primární nebo informační kontakty](#how-do-i-find-out-who-my-primary-or-notices-contact-is).

### <a name="is-onboarding-different-from-migration"></a>Připojení se liší od migrace?
Ano.  Existují dvě fáze v tomto procesu. Nastavení (nebo připojení) vaší organizace před migrací se zajistí, že se nijak nepřeruší práce se změnami jako správce. Jakmile provedeme migraci informací vaší organizace, které pak budou moct spravovat předplatná sady Visual Studio na novém portálu. Pokud primární nebo informační kontakty nemáte připojení před migrací, správci předplatného se zablokuje a nebudete moct spravovat předplatná, dokud dokončit proces zařazení.

### <a name="what-is-the-onboarding-process"></a>Co je proces zařazení do systému?
E-mail je odeslán na primární a informační kontakt vyzývající k dokončení procesu registrace.
Níže jsou pokyny procesu.
1. **Vyhledáním čísla PCN a přihlášení:**

    a. V e-mailu, jsou poskytovány primární a informační kontakt s odkazem na jedinečný a poslední tři číslice z jejich veřejné zákaznické číslo (PCN). *

    b. Aby bylo možné získat celé číslo PCN, třeba adresu primárního kontaktu pro přihlášení k webu VLSC (pokyny k vyhledání PCN najdete níže).

    c. Po získání PCN, budete potřebovat k výběru jejich jedinečného odkazu, která je vyzve k přihlášení. Budou moct přihlásit pomocí pracovní nebo školní účet (Pokud je vaše organizace v Azure AD) nebo účet Microsoft (MSA), pokud vaše organizace se nenachází ve službě Azure AD.

    d. V dalším kroku se zobrazí výzva k zadáte PCN.

2. **Nastavte správce:**

    Jakmile zadáte PCN, že budete přesměrováni na stránku jsou-li přidat supersprávci a správci (dříve označovaní jako manažeři předplatného). V ideálním případě to by se měly dokončit ještě před datem migrace vaší organizace aby nedošlo k žádnému přerušení správy předplatných.

3. **Přístup k novému portálu pro správu předplatného:** Po migraci vaší organizace se pošle e-mailů supersprávci a správcům vyzývající k přístupu na novém portálu a zahájení správy předplatných.

> [!NOTE]
> Pokud primární nebo informační kontakt zobrazí více než jednu e-mailu, to znamená, že mají více než jedno číslo PCN. Bude nutné provést použitím jedinečného odkazu pro číslo PCN odkazuje v každém e-mailu.

### <a name="what-is-the-difference-between-a-super-admin-and-an-administrator"></a>Jaký je rozdíl mezi Supersprávcem a správcem?
Při prvním přihlášení primární nebo informační kontakt, že se automaticky nastaví jako superuživatele. Supersprávci můžete spravovat přístup správce k předplatným přidání nebo odstranění jiných supersprávců, kteří jsou nebo správci a můžete také spravovat předplatná. Super admin můžete přiřadit jiných supersprávců, kteří jsou kromě samotné.

Správci (dříve označovaní jako manažeři předplatného) jsou pouze moct spravovat předplatná, ale nemůžete ovládat, kdo má přístup ke správě přihlášení k odběru.

### <a name="how-will-i-as-an-administrator-onboard-to-the-new-portal"></a>Jak můžu, bude jako správce, připojit k novému portálu?
Primární kontakty a informační kontakt vaší organizace obdrží e-mail s jedinečný odkaz, přejdou na stránku, která umožní uživatelům přihlášení pomocí obou pracovních nebo školních účtů se opírá o Azure Active Directory (Azure AD) nebo osobní účty spravované služby. Po přihlášení bude potřebovat k zadání vaší organizace veřejné zákaznické číslo (PCN) nebo autorizační číslo ověřit smlouvy. Pak se nastaví jako supersprávce moct přidat další správce, jako jste vy, ke správě předplatných sady Visual Studio.

### <a name="where-do-i-manage-subscriptions-if-my-organization-has-been-onboarded-but-hasnt-been-migrated"></a>Kde můžu spravovat předplatná, pokud Moje organizace má byla zařazena do systému, ale nebyla migrována?
Bude pokračovat, spravovat předplatná prostřednictvím webu VLSC až se zobrazí e-mailu z předplatných sady Visual Studio, že vaše organizace je dokončená a je připravené na správu na novém portálu.

### <a name="where-can-i-locate-my-organizations-public-customer-number-pcn-or-authorization-number"></a>Kde najdu veřejné zákaznické číslo (PCN) nebo autorizační číslo mojí organizace?
Přihlaste se k [VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx) a přejít na následující cestu: **Předplatná** > **předplatná sady Visual Studio**. Níže se nachází PCN **výsledky číslo smlouvy/veřejný zákazníka**. Získejte pokyny krok za krokem nalezením vašeho PCN v tomto [článek nápovědy](find-pcn.md).

### <a name="how-do-i-find-out-who-my-primary-or-notices-contact-is"></a>Jak můžu zjistit kdo je primární nebo informační kontakt?
Přihlaste se k [VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx) a přejít na následující cestu: **Licence > Přehled vztahů** vyberte váš **licencování ID > kontakty**. Získejte pokyny krok za krokem k vyhledání primární nebo informační kontakt v tomto [článek nápovědy](find-primary-contact.md).

### <a name="what-if-my-primary-or-notices-contact-is-gone-no-longer-with-the-company-or-not-available-to-complete-onboarding"></a>Co když Moje primární nebo informační kontakt zmizel, už ve společnosti nebo není k dispozici k dokončení registrace?
Budete muset [obraťte se na podporu](https://visualstudio.microsoft.com/subscriptions/support/#talktous) a poskytnout jim e-mail, který jste použili ve VLSC pro správu předplatných. Po ověření bude podpory vám pomůžou v procesu registrace.

### <a name="what-will-happen-with-renewing-customers"></a>Co se stane se zákazníky prodlužující předplatné?
Zákazníky prodlužující předplatné by měly být nadále obnovení svá předplatná obvyklým způsobem, jako obnovení nejsou procesy vliv migrace.

### <a name="should-my-organization-wait-to-set-up-a-new-agreement-in-the-new-system-rather-than-renew-an-existing-agreement"></a>Nastavit novou smlouvu v novém systému, místo prodloužení stávající smlouvy počkat mojí organizace?
Ne.  Migrace nebude mít vliv na vytváření nebo prodloužení smlouvy.

### <a name="what-if-my-organizations-agreement-is-in-the-grace-period-during-the-transition-will-they-also-be-migrated"></a>Co když je smlouva mojí organizace v období odkladu, během přechodu? Bude se také migrovat?
Ano, pokud je smlouva stále aktivní, budou migrovány vaší organizace.

### <a name="what-if-my-organization-has-over-claimed-in-the-current-system-will-we-still-be-migrated-to-the-new-system"></a>Co když Moje organizace používá více deklarací identity v aktuálním systému? Se budeme přesto migrováni na nový systém?
Ano, vaše organizace bude přesto migrována na nový systém. Možnost více deklarací identity (pro smlouvy typy, které to umožňují) budou existovat v novém systému.

### <a name="what-if-my-organization-has-more-than-one-subscription-assigned-to-a-single-useremail-address"></a>Co když Moje organizace má více než jedno předplatné, přiřadit jeden uživatel nebo e-mailovou adresu?
Vaše organizace bude přesto migrována.  Ale nebudete moci přiřazovat další předplatná, stejné úrovně (ie: Enterprise, Professional, atd.) Tento uživatel nebo e-mailovou adresu. Jakékoliv předplatné na základě stejné úrovně, které mají stejnou e-mailovou adresu, po migraci budou se dál zobrazovat, ale správci bude nutné změnit e-mailové adresy, aby byly jedinečné. Nebude moct přiřadit několik předplatných na stejné úrovni jednoho uživatele nebo e-mailovou adresu, na novém portálu.

### <a name="where-can-i-find-the-most-up-to-date-information-about-the-migration"></a>Kde najdete nejnovější informace o migraci
Pro většinu aktuální informace týkající se této migrace, navštivte prosím náš správce předplatných sady Visual Studio [webová stránka](https://aka.ms/vs-admin). Pokud potřebujete podporu, prohlédněte si předplatné sady Visual Studio [stránku podpory](http://visualstudio.microsoft.com/subscriptions/support/#!collections/962-subscriptions), který obsahuje samoobslužné podpory informace a podpora kontaktní informace. Průběhu několika následujících měsíců budeme nadále poskytovat aktualizace na webové stránce správce a prostřednictvím e-mailu, abychom tento přechod dojít s lehkostí a elegancí.

## <a name="resources-and-support-information"></a>Materiály a informace o podpoře
- [Webovou stránku pro správce](https://visualstudio.microsoft.com/subscriptions-administration/)

- Předplatná sady Visual Studio a správu [podpory](https://visualstudio.microsoft.com/subscriptions/support/)

- [Jak najít své číslo PCN](find-pcn.md)

- [Jak najít primární nebo informační kontakt](find-primary-contact.md)

- [Video](https://www.youtube.com/watch?v=ZmnywYGSFMg&list=PLReL099Y5nRfDyvvwzNDBaZe7qTxmuM2T&index=1&t=0s) pro registraci vaší organizace a správě správců
