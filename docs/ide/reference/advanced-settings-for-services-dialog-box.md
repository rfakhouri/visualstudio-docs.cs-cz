---
title: Dialogové okno Pokročilé nastavení služeb
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesAdvancedServices
helpviewer_keywords:
- Advanced Settings for Services dialog box
ms.assetid: 6dde4a2d-85e1-4275-aa55-24b84111be91
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 330f52e1dd72f56c61e2fd77f5150edf4ac30731
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62791959"
---
# <a name="advanced-settings-for-services-dialog-box"></a>Dialogové okno Pokročilé nastavení služeb
Klientské aplikační služby nabízejí zjednodušený přístup ke [!INCLUDE[ajax_current_short](../../ide/reference/includes/ajax_current_short_md.md)] přihlášení, role a služby profilu v aplikacích Windows Forms a Windows Presentation Foundation (WPF). Můžete použít **služby** stránku **Návrháře projektu** konfigurace klientských aplikačních služeb. Další informace o **služby** stránky, přečtěte si téma [stránka služby, Návrhář projektu](../../ide/reference/services-page-project-designer.md).

 Použití **pokročilé nastavení služeb** dialogovému oknu **služby** stránku **Návrháře projektu** nakonfigurovat upřesňující nastavení pro klientské aplikační služby. Pomocí těchto nastavení můžete změnit některé výchozí aplikace služby chování umožňující méně běžné scénáře. Další informace najdete v tématu [klientských aplikačních služeb](/dotnet/framework/common-client-technologies/client-application-services).

 Přístup **pokročilé nastavení služeb** dialogové okno, vyberte uzel projektu v **Průzkumníku řešení**a potom klikněte na tlačítko **vlastnosti** na **projektu**  nabídky. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **služby** kartu a potom klikněte na **Upřesnit** tlačítko. Toto tlačítko bude zakázána, dokud povolit klientské aplikační služby.

## <a name="task-list"></a>Seznam úkolů

- [Postupy: Konfigurace klientských aplikačních služeb](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

 **Uložit hodnoty hash hesla místně umožňující přihlášení offline** Určuje, zda zašifrované heslo uživatele bude do mezipaměti místně a povolit uživateli přihlášení, když je aplikace v režimu offline. Ve výchozím nastavení je vybraná tato možnost.

 **Vyžadovat, aby uživatelé přihlásit znovu pokaždé, když vyprší platnost souboru cookie server** Určuje, zda dříve ověřené uživatele automaticky ověřit při vaše aplikace přistupuje role nebo služby profilů a ověření serveru vypršela platnost souboru cookie. Vyberte tuto možnost, chcete odepřít přístup k aplikačním službám a vyžadují explicitní opětovné ověření po vypršení platnosti souboru cookie. To je užitečné pro aplikace nasazené na veřejných místech, abyste měli jistotu, že uživatelé, kteří neustále spuštěný aplikace po použití zůstat ověření po neomezenou dobu. Tato možnost není ve výchozím nastavení zaškrtnuto.

 **Časový limit mezipaměti služby role** určuje množství času se použití zprostředkovatele rolí klienta do mezipaměti hodnoty role namísto přístupu ke službě role. Nastavte tento časový interval na malou hodnotu při aktualizaci role často nebo větší hodnotu při aktualizaci role zřídka. Výchozí hodnota je jeden den.

 Zprostředkovatel rolí má přístup k hodnoty uložené v mezipaměti role nebo služby role při volání <xref:System.Web.Security.RolePrincipal.IsInRole%2A> metody. Chcete-li programově vymazat mezipaměť a vynutit tato metoda pro přístup k vzdálené službě, zavolejte <xref:System.Web.ClientServices.Providers.ClientRoleProvider.ResetCache%2A> metody.

 **Použijte vlastní připojovací řetězec** Určuje, jestli poskytovatelé služeb klienta bude používat vlastní úložiště dat pro místní mezipaměti. Ve výchozím nastavení použije poskytovatelé místního systému souborů pro ukládání do mezipaměti. Výběrem této možnosti se automaticky vyplní výchozí připojovací řetězec do textového pole. Můžete ponechat výchozí připojovací řetězec k automatickému generování a použití databáze systému SQL Server Compact Edition, nebo můžete zadat připojovací řetězec k existující databázi SQL serveru. Další informace najdete v tématu [jak: Konfigurace klientských aplikačních služeb](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services). Tato možnost není ve výchozím nastavení zaškrtnuto.

## <a name="see-also"></a>Viz také:

- [Klientské aplikační služby](/dotnet/framework/common-client-technologies/client-application-services)
- [Stránka Služby, Návrhář projektu](../../ide/reference/services-page-project-designer.md)
- [Postupy: Konfigurace klientských aplikačních služeb](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)