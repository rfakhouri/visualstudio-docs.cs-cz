---
title: Předplatná sady Visual Studio produktů společnosti Microsoft a smlouvu o poskytování služeb (MPSA) | Dokumentace Microsoftu
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 03/14/2018
ms.topic: conceptual
description: Předplatná sady Visual Studio produktů společnosti Microsoft a smlouvu o poskytování služeb (MPSA)
searchscope: VS Subscription
ms.openlocfilehash: cf0a6c0c7f09cefa70edd0af1dcedf46afdf81bf
ms.sourcegitcommit: cea6187005f8a0cdf44e866a1534a4cf5356208c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/27/2019
ms.locfileid: "56953804"
---
# <a name="visual-studio-subscriptions-in-a-microsoft-products-and-services-agreement-mpsa"></a>Předplatná sady Visual Studio v Microsoft Products a smlouvu Services (MPSA)

Předplatná sady Visual Studio jste zakoupili prostřednictvím programu MPSA, existuje několik věcí, které měli vědět, než se může stát se správcem předplatných sady Visual Studio a přiřazení předplatných pro vaše uživatele. Pokud již byl nastavíte jako správce a potom můžete přejít přímo na předplatná sady Visual Studio [portál pro správu](https://manage.visualstudio.com/).

Jako zákazník MPSA vám představíme na portál, kde můžete spravovat vaše prostředky zakoupená prostřednictvím MPSA. Tento nový portál, nazývá [Business Center](https://businessaccount.microsoft.com/), který podporuje některé stejné a nové funkce, stejně jako Volume Licensing Service Center (VLSC). Patří mezi ně zobrazení vaší licence souhrn objednávek, soubory ke stažení, klíče, uživatelů atd. Však předplatná sady Visual Studio v MPSA chovají podobně jako cloudové služby. Business Center také používá pro přihlášení, místo Microsoft Accounts pracovních účtů. Pokud vaše organizace používá cloudové služby, jako je Office 365 nebo Azure Active Directory a e-mailu je součástí libovolné z těchto dvou služeb je již pracovní účet. To vám umožní registraci do centra pro firmy pomocí existujícího hesla, která vaší organizaci určený pro vás. Pokud vaše organizace nepoužívá cloudových služeb a e-mailu není pracovní účet na všech, Nedělejte si starosti jak může použijte ho k registraci do centra pro firmy.

Kromě toho, předplatná sady Visual Studio [portál pro správu](https://manage.visualstudio.com/) je, kde předplatná se přiřadí pro předplatitele po stát správce sady Visual Studio. V MPSA musí být zřízená předplatná sady Visual Studio na jeho odpovídající management portal, což je portál pro správu předplatných Visual Studio. K tomuto účelu, budete muset postupu přidružte svůj účet nákup na tenanta (například contoso.onmicrosoft.com).

Mějte prosím na paměti, že existují dva typy klientů (nespravovaného tenanta na spravovaného a nespravovaného tenanta). Ke spravovanému tenantovi odkazuje na tenantovi, který je již spravován jako správci v rámci organizace.

Nespravovaného tenanta je tenant bez jakékoli správci v rámci a není použitelné pro Online služby, jako je Office 365. Nespravované tenanti také vytvářejí při registraci do centra pro firmy s e-mailu, který není pracovní účet. Pokud se zobrazí výzva vytvořit heslo při registraci do centra pro firmy, pak to znamená, že e-mailu nebylo pracovní účet a vytvořili nespravovaného tenanta.

Před dokončením přidružení tenanta tady je pár požadavky a kroky potřebné k stát se správcem předplatných sady Visual Studio.

## <a name="pre-tenant-association-managed-tenant"></a>Přidružení předběžné tenanta (spravovaného klienta)

- Musí být registrovaný uživatel k centru pro firmy.
- Uživatel správce (minimálně) nebo globální správce musí být v rámci tenanta, které jsou součástí. (To platí, pokud vaše společnost už používá cloudové služby). Kteroukoli z těchto rolí je potřeba mít oprávnění správce předplatných sady Visual Studio.
- Musíte být globálním správcem tenanta, které jsou součástí budete moci přidružit zakoupení účtu pro vašeho tenanta.
- Musí být účet správce nebo správce účtu v Centru pro firmy.
- "Země nebo oblast" pole v rámci profilu uživatele (a žádný jiný uživatel) v [Azure](https://portal.azure.com/) musí být správně vyplní podle vaší oblasti (například USA, certifikační Autority, atd.). 

> [!NOTE]
> Všichni uživatelé, kteří mají být správce předplatných sady Visual Studio nejsou musí být uživatelé v Centru pro firmy, protože stačí splňují kritéria v krocích 2 a 5.

Po splnění kritérií pro výše uvedené kroky 5 můžete pokračovat k přidružení účtu nákupu do svého tenanta níže uvedeného postupu.
1. Přihlaste se k [centra Business](https://businessaccount.microsoft.com/).
2. Klikněte na **účet** kartě a zvolte **přidružit domén**.
3. Vyberte vaše **nákupu účet** (Pokud máte více než jeden).
4. Vyberte vaše **tenanta** (například contoso.onmicrosoft.com).
5. Klikněte na tlačítko **přidružit domény**.

Po přidružení všem uživatelům potřebné kritériím obvykle zřídí jako správce předplatných sady Visual Studio během několika minut. Nicméně v některých případech může trvat až 24 hodin. Jakmile zřídíte budete mít přístup k portálu správy předplatných Visual Studio. Pokud tento postup trvá déle než 24 hodin, kontaktujte prosím podporu MPSA.

> [!NOTE]
> Pokud existují noví uživatelé, kteří splnění kritérií pro kroky 2 a 5 (po přidružení) obraťte se na podporu MPSA. Podpora MPSA poskytne pomoc zřídit nový správce předplatných sady Visual Studio.

## <a name="tenant-association-unmanaged"></a>Přidružení klienta (nespravovaný)

Pokud jste se zaregistrovali k centru pro firmy s e-mailu, která nebyla pracovní účet (není zaregistrovaný ve službě Azure Active Directory "Azure AD"), jak bylo vysvětleno v odstavci pět výše, přidružení tenanta se bude poněkud lišit. Je potřeba provést, co se nazývá "převzetí domény". Během tohoto procesu vytvoříte sami globálního správce, který se změní váš tenant z nespravovaných do spravovaných.

Podrobnější vysvětlení tohoto procesu, můžete použít [rychlý Start provede](https://www.microsoft.com/en-us/Licensing/existing-customer/business-center-training-and-resources.aspx). Stáhněte si prosím průvodce s názvem *"Instalace a použití vaše Online služeb"* který vás provede převzetí domény. Po dokončení nákupu také bude účet přidružený k vašemu tenantovi.

> [!NOTE]
> Po dokončení procesu převzetí domény, je nutné splnit kritéria z pěti kroků v části pro přidružení Tenanta předem (spravované). Po splnění těchto kritérií, pouze je nutné se obrátit na podporu MPSA zřídit další správce předplatných sady Visual Studio.

Vyžadovat pomoc nebo máte nějaké dotazy, můžete požádat podpory telefonicky nebo e-mailu.

Podpora MPSA: **1-866-200-9611**, k dispozici od pondělí až pátek 5:30:00 do 5:30 hodin tichomořského času

E-mailu: ngvlsup@microsoft.com
