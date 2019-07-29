---
title: Začínáme s portálem pro správu předplatných | Visual Studio Marketplace
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/24/2019
ms.topic: conceptual
description: Naučte se, jak začít spravovat předplatná sady Visual Studio ve vaší organizaci pomocí portálu pro správu předplatných.
ms.openlocfilehash: f3b11a0a0977fff8a6c89f565adffb1cac49e2ad
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605709"
---
# <a name="get-started-with-the-visual-studio-subscriptions-administration-portal"></a>Začínáme s portálem pro správu předplatných sady Visual Studio
Mějte na paměti, že když použijete portál pro správu předplatných sady Visual Studio:
- **Předplatná sady Visual Studio jsou licencovaná na uživatele.** Každý předplatitel může software používat na tolik počítačů, kolik jich je potřeba pro vývoj a testování.
- **Přiřaďte každému předplatiteli jenom jednu úroveň**předplatného, která odpovídá předplatnému sady Visual Studio, které vaše organizace zakoupila. Pokud máte k těmto předplatitelům přiřazenou víc než jednu úroveň předplatného, upravte jejich nastavení tak, aby byla jenom jedna.
- **Úroveň předplatného předplatitele se bude muset aktualizovat** , až se předplatné upgraduje (po zakoupení "podrobné" licence), nebo se obnoví na nižší úrovni.
- **Nesdílejte předplatná mezi předplatiteli.** Předplatná musí být přiřazena k pojmenovaným jednotlivcům.  Přiřazení předplatných týmům se nepovoluje.  Musíte přiřadit předplatné všem, kdo používá celou aplikaci nebo výhody předplatného (software pro vývoj a testování, Microsoft Azure, e-Learning atd.).

## <a name="access-to-the-portal"></a>Přístup k portálu
Pokud jste primární nebo kontaktní kontakt na smlouvu vaší organizace, budete po nastavení multilicenční smlouvy automaticky zřídit přístup k portálu. Obdržíte uvítací e-mail systému aktivovaný systémem a určíte, která e-mailová adresa se má použít k přihlášení na portál. Jakmile se přihlásíte, budete automaticky nastaveni jako správce super a můžete začít spravovat předplatné a jiné správce. 

## <a name="administrator-roles"></a>Role správce
Na novém portálu pro správu předplatných sady Visual Studio existují dvě různé role pro multilicenční zákazníky. Tyto role jsou jako role správce předplatných a role správce předplatných v VLSC v dnešní době.

**Super správci:** Při prvním nastavení organizace se primární nebo informační kontakt ve výchozím nastavení stal nadtypem správce. Primární nebo informační kontakt se může rozhodnout, že přiřadí další superuživatele nebo správce. Správce Super může přidat a odebrat další správce i předplatitele. Pokud je v systému více než dva Super správci, může nadstraněný správce odstranit všechny kromě poslední dvě pro zabezpečení.

**Systémů** Správce může nastavit jenom správce s rolí super. Správce může spravovat předplatitele v rámci smluv, které se k nim správce superuživatele přiřadí.

## <a name="the-subscribers-page"></a>Stránka předplatitelé
Po přiřazení předplatných vám karta předplatitelé poskytne podrobné informace o předplatitelích, včetně těchto:
- Křestní jméno a příjmení každého předplatitele.
- E-mailová adresa pro tohoto uživatele
- Úroveň předplatného, která je jim přiřazena.
- Datum přiřazení jejich předplatného.
- Datum vypršení platnosti předplatného.
- Volitelný textový popis.
- Označení toho, zda bylo stahování odběratele povoleno nebo zakázáno.
- Země, ve které se nacházejí.
- Jazykové předvolby pro e-maily týkající se komunikace přiřazení na portálu pro správu.
- Volitelné pole pro jinou e-mailovou adresu, která se používá pro komunikaci než přihlášení.

Na levé straně této stránky můžete zobrazit další informace o počtu zakoupených, přiřazených a stále dostupných licencí k předplatnému v organizaci pro každou smlouvu.
> [!div class="mx-imgBorder"]
> ![Stránka předplatitelů portálu pro správu předplatných sady Visual Studio](_img/using-admin-portal/subscribers-page.png)

## <a name="the-details-page"></a>Stránka s podrobnostmi
Další informace o zobrazené smlouvě získáte výběrem karty Podrobnosti. Zobrazuje stav smlouvy, účet nákupu, podrobnosti o organizaci, nadřízeného správce a další související informace.
> [!div class="mx-imgBorder"]
> ![Stránka podrobností portálu pro správu předplatných sady Visual Studio](_img/using-admin-portal/details-page.png)

## <a name="next-steps"></a>Další postup
Další informace o zodpovědnostech pro správce:
- [Přehled odpovědností správce](admin-responsibilities.md)
- [Inventář předprodukčního prostředí](admin-inventory.md)
- [Správa velkých týmů a externích dodavatelů](manage-teams.md)
- [Sledování přiřazení uživatelů a zpracování objednávek](assignments-orders.md)
- Použití [maximálního využití](maximum-usage.md) ke sledování závazků nákupu
