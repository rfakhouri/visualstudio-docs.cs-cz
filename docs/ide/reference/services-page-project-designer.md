---
title: Stránka Služby, návrhář projektu
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesServices
helpviewer_keywords:
- Services page in Project Designer
- Project Designer, Services page
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 406e8fbb16d3cac4b755b0532f3916fed486e466
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919006"
---
# <a name="services-page-project-designer"></a>Stránka Služby, návrhář projektu

Klientské aplikační služby poskytují zjednodušený přístup [!INCLUDE[ajax_current_short](../../ide/reference/includes/ajax_current_short_md.md)] k přihlašování, rolím a profilovým službám z aplikací model Windows Forms a Windows Presentation Foundation (WPF). Stránku **služby** **Návrháře projektu** můžete použít k povolení a konfiguraci klientských aplikačních služeb pro svůj projekt.

Pomocí klientských aplikačních služeb můžete pomocí centralizovaného serveru ověřovat uživatele, určit role nebo role přiřazené jednotlivým uživatelům a ukládat nastavení aplikací pro jednotlivé uživatele, která můžete sdílet přes síť. Další informace najdete v tématu [aplikační služby klienta](/dotnet/framework/common-client-technologies/client-application-services).

Chcete-li získat přístup ke stránce **služby** , vyberte uzel projektu v **Průzkumník řešení**a potom klikněte na tlačítko **vlastnosti** v nabídce **projekt** . Když se zobrazí **Návrhář projektu** , klikněte na kartu **služby** .

## <a name="task-list"></a>Seznam úkolů

[Postupy: Nakonfigurovat Aplikační služby klienta](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

 **Konfigurace**

Tento ovládací prvek není na této stránce možné upravovat. Popis tohoto ovládacího prvku naleznete v tématu [Kompilovat stránku, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) nebo [Stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).

 **Platformy**

Tento ovládací prvek není na této stránce možné upravovat. Popis tohoto ovládacího prvku naleznete v tématu [Kompilovat stránku, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) nebo [Stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).

 **Povolit klientské aplikační služby**

Tuto možnost vyberte, pokud chcete povolit klientské aplikační služby. Aby bylo možné používat klientské aplikační služby, je nutné zadat umístění služby na stránce **služby** .

 **Použít ověřování systému Windows**

Označuje, že zprostředkovatel ověřování bude používat ověřování založené na systému Windows, to znamená identitu poskytovanou operačním systémem Windows.

 **Použití ověřování pomocí formulářů**

Označuje, že zprostředkovatel ověřování bude používat ověřování pomocí formulářů. To znamená, že aplikace musí poskytnout uživatelské rozhraní pro přihlášení. Další informace najdete v tématu [jak: Implementace přihlášení uživatele pomocí Aplikační služby](/dotnet/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services)klienta.

 **Umístění ověřovací služby**

Používá se pouze s ověřováním pomocí formulářů. Určuje umístění ověřovací služby.

 **Volitelné Poskytovatel pověření**

Používá se pouze s ověřováním pomocí formulářů. Označuje implementaci, kterou bude služba ověřování používat k zobrazení přihlašovacího dialogového okna, když vaše aplikace `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> volá metodu a předá prázdné řetězce nebo `null` parametry. <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> Pokud toto pole necháte prázdné, musíte do <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> metody předat platné uživatelské jméno a heslo. Je nutné zadat poskytovatele pověření jako název typu kvalifikovaného pro sestavení. Další informace naleznete v tématu <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName> a [názvy sestavení](/dotnet/framework/app-domains/assembly-names). V nejjednodušším tvaru název kvalifikovaného typu sestavení vypadá podobně jako v následujícím příkladu:`MyNamespace.MyLoginClass, MyAssembly`

 **Umístění služby rolí**

Určuje umístění služby rolí.

 **Umístění služby webového nastavení**

Určuje umístění služby Profile (webové nastavení).

 **Pokročilé**

Otevře [dialogové okno Upřesnit nastavení pro služby](../../ide/reference/advanced-settings-for-services-dialog-box.md), které můžete použít k přepsání výchozího chování. Toto dialogové okno můžete například použít k určení databáze pro úložiště offline místo použití místního systému souborů. Další informace najdete v tématu [Pokročilá nastavení pro služby v dialogovém okně](../../ide/reference/advanced-settings-for-services-dialog-box.md).

## <a name="see-also"></a>Viz také:

- [Klientské aplikační služby](/dotnet/framework/common-client-technologies/client-application-services)
- [Dialogové okno Pokročilé nastavení služeb](../../ide/reference/advanced-settings-for-services-dialog-box.md)
- [Postupy: Nakonfigurovat Aplikační služby klienta](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)
- [Stránka Kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)
- [Stránka Sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md)
