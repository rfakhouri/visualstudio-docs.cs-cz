---
title: Pomocí portálu správce | Visual Studio Marketplace
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
mescription: Learn how to manage your organization's Visual Studio subscriptions with the Administrator Portal.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 22351b94923777d5eb1fe40cd2e43e9dc20f2449
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2018
---
#  <a name="using-the-visual-studio-subscriptions-administrator-portal"></a>Pomocí portálu správce předplatných Visual Studio

Mějte na paměti při použití Visual Studio odběry portálu pro správu:
 
- **Visual Studio odběry licenci na uživatele.** Odběratel můžete použít software na jako v mnoha počítačích podle potřeby pro vývoj a testování. 
- **Přiřaďte úroveň jenom jedno předplatné pro každý odběratele**, odpovídající předplatné sady Visual Studio, vaše organizace koupila. Pokud máte Odběratelé, kteří s více než jeden úrovni předplatného, které jsou jim přiřazeny, upravte jejich nastavení tak, aby budou mít pouze jednu. 
- **Úrovni odběratele předplatného bude potřeba aktualizovat** Pokud je předplatné upgradovat (po nákupu licenci "přechody") nebo obnovit na nižší úrovni. 
- **Nesdílí odběry mezi odběratele.** Předplatné je nutné přiřadit k každý, kdo používá nebo jeho část výhody předplatného (software pro vývoj a testování, Microsoft Azure, e učení, atd.). 

## <a name="adminstrator-roles"></a>Role správce

Existují dva různé role, které existují v nové Visual Studio odběry portálu pro správu pro multilicenční zákazníky. Tyto role jsou dnes jako primární nebo oznámení obraťte se na roli a roli odběry Manager v na webu VLSC. 

**Superuživatele admins:** při prvním nastavení organizace, bude primární server nebo obraťte se na oznámení super admin ve výchozím nastavení. Kontakt primární nebo oznámení můžete přiřadit další super admins nebo administrators. Super správce můžete přidávat a odebírat jiné správci, jakož i odběratele. Pokud v systému existuje více než dva super admins, super správce odstranit všechny kromě poslední dva pro zabezpečení. 

**Správci:** správce může nastavit pouze super správce. Správce může spravovat Odběratelé, kteří ve smlouvách, které přiřadí super admin k nim. 

## <a name="getting-started"></a>Začínáme

Chcete-li spravovat odběry vaší organizace pomocí portálu správce, musíte nejdřív zaváděním vaší organizace na portál.  Po dokončení registrace, budete chtít seznámit se s odběratele a podrobnosti stránky, jako jsou ty, kde najdete nástroje a informace, které potřebují k provádění úloh správy vaše předplatné.  

### <a name="onboarding"></a>Registrace

Pokud vaše organizace je připravené k zařazený, nemá pro Visual Studio odběry portálu pro správu e-mailu odešle na primárním serverem a oznámení kontakty vyzvou k dokončení procesu registrace. Níže podrobnosti jsou kroky, které budou muset provedou se budou registrovat do nového portálu. Pokud chcete návod procesu, podívejte se na to [správce registrace video](https://channel9.msdn.com/Series/Visual-Studio-Subscriptions-Administration/Onboarding-your-organization-to-the-new-Visual-Studio-Subscription-Administration-Portal-and-setting) nebo to [článek podpory od](https://support.microsoft.com/help/4013931/visual-studio-subscriptions-administrator-migration-process "Visual Studio odběry správce proces migrace").   
1.  **Vyhledání vašeho kontrolního čísla výrobku a přihlášení:**
    - V e-mailu, primárním serverem a kontakty oznámení jsou jedinečný odkaz a za poslední tři číslice z jejich veřejné zákaznické číslo (kontrolního čísla výrobku). * 
    - Chcete-li získat celý kontrolního čísla výrobku, primárního kontaktu muset přihlásit k webu VLSC (pokyny týkající se umísťování kontrolního čísla výrobku naleznete existuje). 
    - Po získání kontrolního čísla výrobku, budete potřebovat k výběru jejich jedinečný odkaz, který se výzva k přihlášení. Bude moct přihlásit pomocí pracovní nebo školní účet (Pokud je vaše organizace na AAD) nebo účet Microsoft (MSA), pokud vaše organizace není v AAD. 
    - V dalším kroku se bude nutné zadat kontrolního čísla výrobku. 
2.  **Nastavte správce.** Po zadání kontrolního čísla výrobku, budou se zaregistruje jako superuživatele správce v novém systému a budete moct přidat další super správci a správci (dříve označovaný jako správce předplatného). Aby nedošlo ke ztrátě přístupu, to by se měly dokončit před datem migrace vaší organizace. 
3.  **Přístup k portálu pro správu nové předplatné.**  Po migraci vaší organizace, odešle e-mailů pro nově přidaného super správci a správci pozváním pro přístup k portálu nový a začít spravovat odběry.  

> [!NOTE]
> Pokud primární server nebo oznámení kontakty zobrazí více než jeden e-mailu, znamená to, že mají více než jeden kontrolního čísla výrobku. Bude nutné k dokončení procesu pomocí jedinečný odkaz pro kontrolního čísla výrobku, kterou se odkazuje v každém email.*

Pokud potřebujete přidat do nové Visual Studio odběry portálu pro správu a nejste si jisti, který je primární nebo oznámení kontaktu, můžete najít tyto informace po přihlášení k [VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx). Podívejte se na [najít vaše primárního kontaktu](/find-primary-contact/) tématu kroky, jak najít kontakt primární nebo oznámení v na webu VLSC.
Pokud jste již byla nastavili jako správce, pak můžete přejít přímo na [Visual Studio portálu pro správu předplatných](https://manage.visualstudio.com).

### <a name="understanding-the-subscribers-page"></a>Vysvětlení stránky odběratele
Jakmile jste přiřadili odběry, kartě odběratele poskytuje podrobné informace o vaší odběratele, včetně:
- První a poslední název každého odběratele.
- E-mailovou adresu pro tohoto uživatele.
- Úroveň předplatného, která jim byla přiřazena.
- Datum, byl přiřazen svoje předplatné. 
- Datum vypršení platnosti pro svoje předplatné.
- Volitelné textový popis.
- Údaj o tom, zda stáhne odběratele byla povolena nebo zakázána. 
- Země, ve které se nacházejí.
- Jejich preferovaný jazyk pro e-mailu, přiřazení komunikace z portálu pro správu.
- Volitelné pole pro jinou e-mailovou adresu pro komunikaci, než přihlášení. 

Na levé straně na této stránce se zobrazí další informace o počtu licencí předplatné zakoupené, přiřazené a stále k dispozici ve vaší organizaci pro každá smlouva.

   ![Stránky Subscibers portál pro správu předplatných sady Visual Studio](_img/using-admin-portal/subscribers-page.png)

### <a name="understanding-the-details-page"></a>Stránce s podrobnostmi o vysvětlení
Další informace o smlouvu, že si prohlížíte vyberte kartu s podrobnostmi. Zobrazuje stav smlouvy, nákupu účet, podrobnosti org, primární kontakty (VLSC), super admins (Pokud je k dispozici) a jiné související informace.

   ![Stránka podrobností portál pro správu předplatných sady Visual Studio](_img/using-admin-portal/details-page.png)

