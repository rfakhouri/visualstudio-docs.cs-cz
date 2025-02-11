---
title: Předplatná sady Visual Studio v rámci smlouvy o produktech a službách společnosti Microsoft (MPSA) | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/23/2019
ms.topic: conceptual
description: Předplatná sady Visual Studio v rámci smlouvy o produktech a službách společnosti Microsoft (MPSA)
ms.openlocfilehash: f87a77cdc19244ca24da1685c0b05372f6cc76d7
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605845"
---
# <a name="visual-studio-subscriptions-in-a-microsoft-products-and-services-agreement-mpsa"></a>Předplatná sady Visual Studio v rámci smlouvy o produktech a službách společnosti Microsoft (MPSA)
Pokud jste si zakoupili předplatná sady Visual Studio prostřednictvím programu MPSA, měli byste si být vědomi, že před tím, než se stanete správcem předplatných sady Visual Studio a přiřadíte odběry uživatelům. Pokud jste již nastavili jako správce, můžete přejít přímo na [portál pro správu](https://manage.visualstudio.com/)předplatných sady Visual Studio.

Zákazníci MPSA nyní spravují prostředky zakoupené prostřednictvím MPSA na novém portálu s názvem [Business Center](https://businessaccount.microsoft.com/Customer), který podporuje funkce podobně jako na webu Volume Licensing Service Center (VLSC). Patří mezi ně zobrazení souhrnu licencí, objednávek, souborů ke stažení, klíčů, uživatelů atd. Předplatná sady Visual Studio v MPSA se však chovají podobně jako Cloud Services. Centrum Business Center také používá pracovní účty k přihlašování místo účtů Microsoft (MSA). Pokud vaše organizace používá cloudové služby, jako je například Office 365 nebo Azure Active Directory, a váš e-mail je součástí některé z těchto dvou služeb, již je to pracovní účet. To vám umožní zaregistrovat se do centra pro firmy s vaším stávajícím heslem. Pokud vaše organizace nepoužívá cloudové služby a váš e-mail není pracovní účet, můžete ho použít k registraci do obchodního centra.

Kromě toho [portál pro správu](https://manage.visualstudio.com/) předplatných sady Visual Studio je místo, kde se přiřadí předplatitelé, jakmile se stanete správcem předplatných sady Visual Studio. V MPSA musí být předplatná sady Visual Studio zřízena na příslušný portál pro správu, což je portál pro správu předplatných sady Visual Studio. K tomu je potřeba přidružit svůj nákupní účet ke klientovi (tj. contoso.onmicrosoft.com).

Všimněte si, že existují dva typy klientů spravovaných klienty a nespravovaných tenantů. Spravovaný tenant odkazuje na tenanta, který už spravuje správci v rámci organizace.

Nespravovaný tenant je tenant bez přiřazených správců a není použitelný pro online služby, jako je například Office 365. Nespravované klienty se vytvoří také při registraci do obchodního centra pomocí e-mailu, který není pracovním účtem. Pokud jste byli požádáni o vytvoření hesla při registraci do obchodního centra, znamená to, že váš e-mail nebyl pracovní účet a vytvořil nespravovaného tenanta.

Tady je několik požadavků/kroků potřebných k tomu, abyste se stali správcem předplatných sady Visual Studio před dokončením přidružení tenanta.

## <a name="pre-tenant-association-managed-tenant"></a>Přidružení před tenantovi (spravovaný tenant)
- Musíte být registrovaným uživatelem služby Business Center.
- Musíte být správcem uživatelů (minimálně) nebo globálním správcem v rámci tenanta, kterého jste členem. (To platí, pokud vaše společnost už používá Cloud Services). Kterákoli z rolí musí být správce předplatných sady Visual Studio.
- Abyste mohli k vašemu tenantovi přidružit svůj nákupní účet, musíte být globálním správcem v tenantovi, který jste členem.
- Musíte být správcem účtu nebo správcem účtů v centru podnikání.
- Pole země nebo oblast v rámci vašeho uživatelského profilu (a jakýkoli jiný uživatel) v [Azure](https://portal.azure.com/) se musí správně naplnit v závislosti na vaší oblasti (například USA, CA atd.). 

> [!NOTE]
> Všichni uživatelé, u kterých chcete, aby správci předplatných sady Visual Studio nemuseli být uživateli v obchodním centru, protože potřebují splňovat kritéria 2 a 5.

Jakmile splníte kritéria výše, můžete k vašemu tenantovi přidružit svůj nákupní účet podle následujících kroků.
1. Přihlaste se do [centra Business Center](https://businessaccount.microsoft.com/Customer).
2. Klikněte na kartu **účet** a vyberte **přidružit domény**.
3. Vyberte svůj **Nákupní účet** (Pokud máte víc než jeden).
4. Vyberte svého **tenanta** (například contoso.onmicrosoft.com).
5. Klikněte na **přidružit doménu**.

Při přidružení budou všichni uživatelé, kteří splňují kritéria, obvykle zřizovat jako správci předplatných sady Visual Studio během několika minut. V časech ale může trvat až 24 hodin. Po zřízení tenanta budete mít přístup k portálu pro správu předplatných sady Visual Studio. Pokud bude trvat déle než 24 hodin, obraťte se prosím na podporu MPSA.

> [!NOTE]
> Pokud existují noví uživatelé, kteří splňují kritéria v krocích 2 a 5 (po přidružení), musíte se obrátit na podporu MPSA. Podpora MPSA vám poskytne pomoc při zřizování nových správců předplatných sady Visual Studio.

## <a name="tenant-association-unmanaged"></a>Přidružení tenanta (nespravované)
Pokud jste se zaregistrovali do centra Business Center pomocí e-mailu, který nebyl pracovním účtem (není zaregistrován v Azure Active Directory "Azure AD"), jak je vysvětleno výše, přidružení tenanta se mírně liší. Budete muset provést akci, která se nazývá "převzetí služeb při selhání domény". Během tohoto procesu sami provedete globálního správce, který změní vašeho tenanta z nespravovaného na spravované.

Pro podrobnější vysvětlení tohoto procesu můžete použít [průvodce rychlé zprovoznění](https://www.microsoft.com/en-us/Licensing/existing-customer/business-center-training-and-resources.aspx). Stáhněte si prosím příručku s názvem *"Setup" a použijte své online služby* , které vás provedou převzetím domény. Až to dokončíte, Váš nákupní účet se taky přidruží k vašemu tenantovi.

> [!NOTE]
> Po dokončení procesu převzetí domény musíte dodržovat kritéria z pěti kroků v části pro přidružení předběžného tenanta (spravované). Jakmile jsou kritéria splněná, bude nutné, abyste se obrátili na podporu MPSA a zřídili další správce předplatných sady Visual Studio.