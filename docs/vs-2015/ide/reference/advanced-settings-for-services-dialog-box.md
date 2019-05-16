---
title: Upřesňující nastavení pro dialogové okno služby | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesAdvancedServices
helpviewer_keywords:
- Advanced Settings for Services dialog box
ms.assetid: 6dde4a2d-85e1-4275-aa55-24b84111be91
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: aa661f48a04057bae8db86e7215a6fc7cafbcfe4
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65699837"
---
# <a name="advanced-settings-for-services-dialog-box"></a>Dialogové okno Pokročilé nastavení služeb
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Klientské aplikační služby nabízejí zjednodušený přístup ke [!INCLUDE[ajax_current_short](../../includes/ajax-current-short-md.md)] přihlášení, role a služby profilu v aplikacích Windows Forms a Windows Presentation Foundation (WPF). Můžete použít **služby** stránku **Návrháře projektu** konfigurace klientských aplikačních služeb. Další informace o **služby** stránky, přečtěte si téma [stránka služby, Návrhář projektu](../../ide/reference/services-page-project-designer.md).  
  
 Použití **pokročilé nastavení služeb** dialogovému oknu **služby** stránku **Návrháře projektu** nakonfigurovat upřesňující nastavení pro klientské aplikační služby. Pomocí těchto nastavení můžete změnit některé výchozí aplikace služby chování umožňující méně běžné scénáře. Další informace najdete v tématu [klientských aplikačních služeb](https://msdn.microsoft.com/library/1487d8df-089e-4f21-abfb-a791a652b58e).  
  
 Přístup **pokročilé nastavení služeb** dialogové okno, vyberte uzel projektu v **Průzkumníku řešení**a potom klikněte na tlačítko **vlastnosti** na **projektu**  nabídky. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **služby** kartu a potom klikněte na **Upřesnit** tlačítko. Toto tlačítko bude zakázána, dokud povolit klientské aplikační služby.  
  
## <a name="task-list"></a>Seznam úkolů  
 [Postupy: Konfigurace klientských aplikačních služeb](https://msdn.microsoft.com/library/34a8688a-a32c-40d3-94be-c8e610c6a4e8)  
  
 [Postupy: Práce Offline u klientských aplikačních služeb](https://msdn.microsoft.com/f792cb16-8520-4a0f-9dc9-07bfbc454e38)  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Uložit hodnoty hash hesla místně pro povolení offline přihlášení**  
 Určuje, zda zašifrované heslo uživatele bude do mezipaměti místně a povolit uživateli přihlášení, když je aplikace v režimu offline. Další informace najdete v tématu [jak: Práce Offline u klientských aplikačních služeb](https://msdn.microsoft.com/f792cb16-8520-4a0f-9dc9-07bfbc454e38). Ve výchozím nastavení je vybraná tato možnost.  
  
 **Vyžadovat, aby uživatelé přihlásit znovu pokaždé, když vyprší platnost souboru cookie serveru**  
 Určuje, zda dříve ověřeným uživatelům automaticky ověřit při vaše aplikace přistupuje role nebo služby profilů a vypršela platnost souboru cookie pro ověřování serveru. Vyberte tuto možnost, chcete odepřít přístup k aplikačním službám a vyžadují explicitní opětovné ověření po vypršení platnosti souboru cookie. To je užitečné pro aplikace nasazené na veřejných místech, abyste měli jistotu, že uživatelé, kteří neustále spuštěný aplikace po použití zůstat ověření po neomezenou dobu. Tato možnost není ve výchozím nastavení zaškrtnuto.  
  
 **Časový limit mezipaměti služby role**  
 Určuje množství času zprostředkovatele rolí klienta použije hodnoty uložené v mezipaměti role namísto přístupu ke službě role. Nastavte tento časový interval na malou hodnotu při aktualizaci role často nebo větší hodnotu při aktualizaci role zřídka. Výchozí hodnota je jeden den.  
  
 Zprostředkovatel rolí má přístup k hodnoty uložené v mezipaměti role nebo služby role při volání <xref:System.Web.Security.RolePrincipal.IsInRole%2A> metody. Chcete-li programově vymazat mezipaměť a vynutit tato metoda pro přístup k vzdálené službě, zavolejte <xref:System.Web.ClientServices.Providers.ClientRoleProvider.ResetCache%2A> metody.  
  
 **Použijte vlastní připojovací řetězec**  
 Určuje, zda poskytovatelů služeb klienta používat vlastní úložiště dat pro místní mezipaměti. Ve výchozím nastavení použije poskytovatelé místního systému souborů pro ukládání do mezipaměti. Výběrem této možnosti se automaticky vyplní výchozí připojovací řetězec do textového pole. Můžete ponechat výchozí připojovací řetězec k automatickému generování a použití databáze systému SQL Server Compact Edition, nebo můžete zadat připojovací řetězec k existující databázi SQL serveru. Další informace najdete v tématu [jak: Konfigurace klientských aplikačních služeb](https://msdn.microsoft.com/library/34a8688a-a32c-40d3-94be-c8e610c6a4e8). Tato možnost není ve výchozím nastavení zaškrtnuto.  
  
## <a name="see-also"></a>Viz také  
 [Klientské aplikační služby](https://msdn.microsoft.com/library/1487d8df-089e-4f21-abfb-a791a652b58e)   
 [Stránka služby, Návrhář projektu](../../ide/reference/services-page-project-designer.md)   
 [Postupy: Konfigurace klientských aplikačních služeb](https://msdn.microsoft.com/library/34a8688a-a32c-40d3-94be-c8e610c6a4e8)   
 [Postupy: Práce Offline u klientských aplikačních služeb](https://msdn.microsoft.com/f792cb16-8520-4a0f-9dc9-07bfbc454e38)
