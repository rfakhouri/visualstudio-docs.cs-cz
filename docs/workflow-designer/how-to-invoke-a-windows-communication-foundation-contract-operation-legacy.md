---
title: 'Návrhář postupu provádění - postupy: volání Windows Communication Foundation kontrakt operace (zastaralé)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: a9058345-708f-4fcf-8739-2a43e5285b7a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b39d2132b29ec1f8fbfd8339bdb8f81e6f752a0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974715"
---
# <a name="how-to-invoke-a-windows-communication-foundation-contract-operation-legacy"></a>Postupy: volání Windows Communication Foundation kontrakt operace (zastaralé)

Toto téma popisuje, jak má být vyvolán operaci kontraktu Windows Communication Foundation (WCF) pomocí návrháře pracovních postupů starší verze Windows s cílem rozhraní .NET Framework verze 3.5 nebo WinFX.

Po přetažení **SendActivity** aktivity z panelu nástrojů na plochu návrháře pracovního postupu importovat existující smlouvy. Určit, které operace je volána z tohoto **SendActivity** aktivity. Vyberte kontrakt a jeho operací prostřednictvím [zvolte operaci dialogové okno (zastaralé)](../workflow-designer/choose-operation-dialog-box-legacy.md).

Navíc pokud používáte konfigurační soubor s vaší služby, je třeba zadat <xref:System.Workflow.Activities.ChannelToken>. <xref:System.Workflow.Activities.ChannelToken> Identifikuje vaši aktivitu odesílání se bude používat pro připojení ke službě pracovního postupu konfiguraci koncového bodu.

## <a name="to-invoke-a-wcf-contract-operation-from-a-sendactivity-activity"></a>K vyvolání operaci kontraktu WCF z SendActivity aktivity

1.  Dvakrát klikněte **SendActivity** aktivity v Návrháři nebo klikněte na tlačítko se třemi tečkami vedle **ServiceOperationInfo** vlastnost v **vlastnosti** podokně.

2.  Když **zvolte operaci** otevře se dialogové okno, klikněte na tlačítko **Import** v pravém horním rohu dialogu.

     [Procházet a vybrat .NET typ dialogové okno (zastaralé)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) otevře.

3.  Sestavení nebo projekt, který obsahuje smlouvu, kterou chcete vyhledat.

4.  Zvolte smlouvu a klikněte na tlačítko **OK**.

5.  V části **dostupné operace**, vyberte operaci, kterou má vyvolat, a klikněte na tlačítko **OK**.

## <a name="to-specify-a-channel-token"></a>Chcete-li zadat token kanálu

1.  Vyberte <xref:System.Workflow.Activities.SendActivity> aktivity v návrháři.

2.  V **vlastnosti** podokně, zadejte název <xref:System.Workflow.Activities.ChannelToken>. Tento název jednoznačně identifikuje token kanálu.

3.  Rozbalte uzel tokenu kanál a zadejte název pro koncový bod klienta, které chcete použít v <xref:System.Workflow.Activities.ChannelToken.EndpointName%2A> pole. Konfigurace koncového bodu se stejným názvem v konfiguračním souboru se používá ke konfiguraci kanálu.

4.  Vytvořte konfiguraci koncového bodu v konfiguračním souboru, pokud ho ještě neexistuje. Další informace o konfiguraci vašeho klienta najdete v tématu [klienta WCF – přehled](/dotnet/framework/wcf/wcf-client-overview).

## <a name="see-also"></a>Viz také

- [Dialogové okno Zvolit operaci (starší verze)](../workflow-designer/choose-operation-dialog-box-legacy.md)
- [Postupy: implementace kontraktu operace s WCF (zastaralé)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)
- [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)