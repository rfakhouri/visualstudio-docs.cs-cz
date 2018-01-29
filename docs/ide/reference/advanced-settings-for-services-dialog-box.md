---
title: "Upřesňující nastavení pro dialogové okno služby | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.ProjectPropertiesAdvancedServices
helpviewer_keywords:
- Advanced Settings for Services dialog box
ms.assetid: 6dde4a2d-85e1-4275-aa55-24b84111be91
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 264f90329bfbf969f50dbc38073bdda26987fd26
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="advanced-settings-for-services-dialog-box"></a>Dialogové okno Pokročilé nastavení služeb
Klient aplikačních služeb poskytují zjednodušenou přístup k [!INCLUDE[ajax_current_short](../../ide/reference/includes/ajax_current_short_md.md)] přihlášení, rolí a profilu služby z aplikací Windows Forms a Windows Presentation Foundation (WPF). Můžete použít **služby** stránku **Návrhář projektu** konfigurace klientských aplikačních služeb. Další informace o **služby** stránky najdete v tématu [stránka služby, Návrhář projektu](../../ide/reference/services-page-project-designer.md).  
  
 Použití **pokročilé nastavení služeb** dialogové okno s **služby** stránky v **Návrhář projektu** můžete nakonfigurovat upřesňující nastavení pro klientské aplikační služby. Pomocí těchto nastavení můžete přepsat některé chování výchozí aplikace služby k povolení méně častých scénářů. Další informace najdete v tématu [klientské aplikační služby](/dotnet/framework/common-client-technologies/client-application-services).  
  
 Pro přístup k **pokročilé nastavení služeb** dialogové okno, vyberte uzel projektu v **Průzkumníku řešení**a potom klikněte na **vlastnosti** na **projektu**  nabídky. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **služby** a pak klikněte **Upřesnit** tlačítko. Toto tlačítko bude zakázána, dokud nepovolíte klientské aplikační služby.  
  
## <a name="task-list"></a>Seznam úloh

- [Postupy: Konfigurace klientských aplikačních služeb](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

 **Uložit hodnoty hash hesla místně pro povolení offline přihlášení**  
 Určuje, zda šifrovaném formátu hesla uživatele bude do mezipaměti místně umožnit uživatelům přihlášení, když je aplikace v režimu offline. Tato možnost je vybrána ve výchozím nastavení.
  
 **Vyžadovat, aby se znovu přihlaste vždy, když vyprší platnost souboru cookie serveru uživatelé**  
 Určuje, zda dříve ověření uživatelé jsou automaticky k novému ověření když vaše aplikace používá role nebo profilu služby a vypršela platnost souboru cookie pro ověřování serveru. Vyberte tuto možnost, chcete odepřít přístup k aplikační služby a vyžadují explicitní opětovné ověření po vypršení platnosti souboru cookie. To je užitečné pro aplikace nasazené na veřejných místech, abyste měli jistotu, že uživatelé, kteří nechte aplikace spuštěna po použití zůstat ověří po neomezenou dobu. Tato možnost není ve výchozím nastavení zaškrtnuté.  
  
 **Časový limit mezipaměti služby role**  
 Určuje množství času zprostředkovatele rolí klienta bude používat hodnoty v mezipaměti role místo přístupu ke službě role. Tento časový interval nastavená na hodnotu malé, když jsou aktualizovány role často nebo na hodnotu větší nebo když role jsou aktualizovány zřídka. Výchozí hodnota je jeden den.  
  
 Zprostředkovatele rolí přistupuje hodnoty v mezipaměti role nebo službu role při volání <xref:System.Web.Security.RolePrincipal.IsInRole%2A> metoda. Pokud chcete prostřednictvím kódu programu vymažete mezipaměť a vynutit tato metoda pro přístup ke vzdálené službě, zavolejte <xref:System.Web.ClientServices.Providers.ClientRoleProvider.ResetCache%2A> metoda.  
  
 **Použít vlastní připojovací řetězec**  
 Určuje, zda poskytovatelé služeb klienta použije vlastní úložiště dat pro místní mezipaměti. Ve výchozím nastavení použije poskytovatelé služeb místního systému souborů pro ukládání do mezipaměti. Výběrem této možnosti bude automaticky vyplnit textové pole s výchozí připojovací řetězec. Můžete ponechat výchozí připojovací řetězec k automatickému generování a použít databázi SQL Server Compact Edition, nebo můžete zadat připojovací řetězec k existující databázi systému SQL Server. Další informace najdete v tématu [postupy: Konfigurace klientských aplikačních služeb](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services). Tato možnost není ve výchozím nastavení zaškrtnuté.  
  
## <a name="see-also"></a>Viz také

[Klientské aplikační služby](/dotnet/framework/common-client-technologies/client-application-services)  
[Stránka Služby, Návrhář projektu](../../ide/reference/services-page-project-designer.md)  
[Postupy: Konfigurace klientských aplikačních služeb](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)