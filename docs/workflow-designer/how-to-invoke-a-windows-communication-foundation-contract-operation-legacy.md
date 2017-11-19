---
title: "Postupy: volání Windows Communication Foundation kontrakt operace (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a9058345-708f-4fcf-8739-2a43e5285b7a
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 51b20275f63b47d607679e04ff061cf77b0d9f90
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-invoke-a-windows-communication-foundation-contract-operation-legacy"></a>Postupy: volání Windows Communication Foundation kontrakt operace (zastaralé)
Toto téma popisuje, jak má být vyvolán [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] smlouvy operace pomocí starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] s cílem [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Po přetahování **SendActivity** aktivity z panelu nástrojů na plochu návrháře pracovního postupu, musíte importovat existující smlouvy a určit, které operace se bude volána z tohoto **SendActivity** aktivita. Můžete vybrat smlouva a jeho operací prostřednictvím [zvolte operaci dialogové okno (zastaralé)](../workflow-designer/choose-operation-dialog-box-legacy.md).  
  
 Navíc pokud používáte konfigurační soubor s vaší služby, je potřeba zadat <xref:System.Workflow.Activities.ChannelToken>. <xref:System.Workflow.Activities.ChannelToken> Identifikuje vaši aktivitu odesílání se bude používat pro připojení ke službě pracovního postupu konfiguraci koncového bodu.  
  
### <a name="to-invoke-a-wcf-contract-operation-from-a-sendactivity-activity"></a>K vyvolání operaci kontraktu WCF z SendActivity aktivity  
  
1.  Dvakrát klikněte **SendActivity** aktivity v Návrháři nebo klikněte na tlačítko se třemi tečkami vedle **ServiceOperationInfo** vlastnost v **vlastnosti** podokně.  
  
2.  Když **zvolte operaci** otevře se dialogové okno, klikněte na tlačítko **Import** v pravém horním rohu dialogu.  
  
     [Procházet a vybrat .NET typ dialogové okno (zastaralé)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) otevře.  
  
3.  Sestavení nebo projekt, který obsahuje smlouvu, kterou chcete vyhledat.  
  
4.  Zvolte smlouvu a klikněte na tlačítko **OK**.  
  
5.  V části **dostupné operace**, vyberte operaci, kterou má vyvolat, a klikněte na tlačítko **OK**.  
  
### <a name="to-specify-a-channel-token"></a>Chcete-li zadat token kanálu  
  
1.  Vyberte <xref:System.Workflow.Activities.SendActivity> aktivity v návrháři.  
  
2.  V **vlastnosti** podokně, zadejte název <xref:System.Workflow.Activities.ChannelToken>. Tento název jednoznačně identifikuje token kanálu.  
  
3.  Rozbalte uzel tokenu kanál a zadejte název pro koncový bod klienta, které chcete použít v <xref:System.Workflow.Activities.ChannelToken.EndpointName%2A> pole. Konfigurace koncového bodu se stejným názvem v konfiguračním souboru se použije ke konfiguraci kanálu.  
  
4.  Vytvořte konfiguraci koncového bodu v konfiguračním souboru, pokud ho ještě neexistuje. Další informace o konfiguraci vašeho klienta najdete v tématu [klienta WCF – přehled](/dotnet/framework/wcf/wcf-client-overview).  
  
## <a name="see-also"></a>Viz také  
 [Výběr dialogové okno operace (zastaralé)](../workflow-designer/choose-operation-dialog-box-legacy.md)   
 [Postupy: implementace kontraktu operace s WCF (zastaralé)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Aktivity pracovního postupu starší verze](../workflow-designer/legacy-workflow-activities.md)