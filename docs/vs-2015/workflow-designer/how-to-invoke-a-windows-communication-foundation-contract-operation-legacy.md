---
title: 'Postupy: Vyvolání operace Windows Communication Foundation kontraktu (starší verze) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: a9058345-708f-4fcf-8739-2a43e5285b7a
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1398d7fb62943c04ca026175a3f46b282bf6da69
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65696322"
---
# <a name="how-to-invoke-a-windows-communication-foundation-contract-operation-legacy"></a>Postupy: Vyvolání operace kontraktu technologie Windows Communication Foundation (starší verze)
Toto téma popisuje, jak vyvolat [!INCLUDE[indigo1](../includes/indigo1-md.md)] smlouvy operace pomocí starší verze [!INCLUDE[wfd1](../includes/wfd1-md.md)] , který cílí [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Po přetažení **SendActivity** aktivitu z panelu nástrojů na plochu návrháře pracovních postupů, musíte importovat existující kontrakt a určit, jaké operace, který bude vyvolán od **SendActivity** aktivita. Vyberte vaše smlouva a jeho operace, ať už [zvolte operaci dialogové okno (starší verze)](../workflow-designer/choose-operation-dialog-box-legacy.md).  
  
 Navíc pokud použijete konfiguračního souboru ve vaší službě, budete muset zadat <xref:System.Workflow.Activities.ChannelToken>. <xref:System.Workflow.Activities.ChannelToken> Identifikuje vaše aktivity odeslání bude používat pro připojení ke službě pracovního postupu konfigurace koncového bodu.  
  
### <a name="to-invoke-a-wcf-contract-operation-from-a-sendactivity-activity"></a>K vyvolání operace kontraktu WCF z SendActivity aktivity  
  
1. Dvakrát klikněte **SendActivity** aktivity v Návrháři nebo klikněte na tři tečky vedle položky **ServiceOperationInfo** vlastnost v **vlastnosti** podokně.  
  
2. Když **zvolte operaci** zobrazí se dialogové okno, klikněte na tlačítko **Import** v pravém horním rohu dialogového okna.  
  
     [Procházet a vybrat typ dialogovému oknu rozhraní .NET (starší verze)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) otevře.  
  
3. Vyhledejte sestavení nebo projekt, který obsahuje kontrakt, který chcete.  
  
4. Zvolte smlouvu a klikněte na tlačítko **OK**.  
  
5. V části **dostupné operace**, vyberte operaci, která chcete vyvolat a klikněte na tlačítko **OK**.  
  
### <a name="to-specify-a-channel-token"></a>K určení tokenu kanálu  
  
1. Vyberte <xref:System.Workflow.Activities.SendActivity> aktivity v návrháři.  
  
2. V **vlastnosti** podokně, zadejte název <xref:System.Workflow.Activities.ChannelToken>. Tento název jednoznačně identifikuje token kanálu.  
  
3. Rozbalte uzel token kanálu a zadejte název pro koncový bod klienta, které budete používat v <xref:System.Workflow.Activities.ChannelToken.EndpointName%2A> pole. Konfigurace koncového bodu se stejným názvem v konfiguračním souboru se použije ke konfiguraci kanálu.  
  
4. Pokud ho ještě neexistuje, vytvořte v konfiguračním souboru konfigurace koncového bodu. Další informace o konfiguraci vašeho klienta najdete v tématu [přehled klientů WCF](https://msdn.microsoft.com/library/f60d9bc5-8ade-4471-8ecf-5a07a936c82d).  
  
## <a name="see-also"></a>Viz také  
 [Zvolte dialogové okno operaci (starší verze)](../workflow-designer/choose-operation-dialog-box-legacy.md)   
 [Postupy: Implementace operace kontraktu WCF (starší verze)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)