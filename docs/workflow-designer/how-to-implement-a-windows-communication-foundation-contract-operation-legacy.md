---
title: "Postupy: implementace Windows Communication Foundation kontrakt operace (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d6aeb20e-fac8-4a9d-bd26-ae78bef96b41
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 8800055878c53adce195bbf7078da410c12128da
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-a-windows-communication-foundation-contract-operation-legacy"></a>Postupy: implementace Windows Communication Foundation kontrakt operace (zastaralé)
Toto téma popisuje, jak implementovat [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] smlouvy operace pomocí starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] s cílem [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Po přetahování **ReceiveActivity** aktivity z panelu nástrojů na plochu návrháře pracovního postupu, buď vytvoříte novou [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] smlouvy nebo importovat existující smlouvy a implementovat operace. Vyberte nebo vytvořte smlouva a jeho operací prostřednictvím [zvolte operaci dialogové okno (zastaralé)](../workflow-designer/choose-operation-dialog-box-legacy.md).  
  
### <a name="to-implement-a-wcf-contract-operation"></a>K implementaci kontraktu operace s WCF  
  
1.  Dvakrát klikněte **ReceiveActivity** aktivity v Návrháři nebo klikněte na tlačítko se třemi tečkami vedle **ServiceOperationInfo** vlastnost v **vlastnosti** podokně.  
  
2.  Proveďte jednu z těchto akcí:  
  
    -   Klikněte na tlačítko **přidat smlouvy** v pravém horním rohu dialogu. Tím se vytvoří nový [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] kontrakt a operace pro vás.  
  
         -nebo-  
  
    -   Klikněte na tlačítko **Import** v pravém horním rohu dialogu. [Procházet a vybrat .NET typ dialogové okno (zastaralé)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) otevře. Sestavení nebo projekt, který obsahuje smlouvu, kterou chcete vyhledat. Zvolte smlouvu a klikněte na tlačítko **OK**.  
  
     Po vytvoření kontraktu nebo importovat, můžete přidat nové operace s touto smlouvou vytvořené nebo importované. Chcete-li přidat novou operaci, zvolte smlouvu a klikněte na **přidat operace** v pravém horním rohu dialogu. Po dokončení operace přidávání, pokračujte krokem 3.  
  
3.  Vyberte operaci, kterou chcete přidružit **ReceiveActivity** aktivity. Definice operace můžete upravit tak, že změníte název operace, parametry, vlastnosti a nastavení oprávnění.  
  
     Chcete-li změnit název, zadejte nový název v **název operace** textové pole.  
  
     Klikněte **parametry** karty pro přístup k parametrům operace. Můžete změnit název, typ nebo směr parametru a také přidat nebo odstranit parametry z operace.  
  
     Klikněte **vlastnosti** karty pro přístup k funkci operaci ochrany úrovně a podporované zpráva exchange operace.  
  
     Klikněte **oprávnění** určete, které skupiny jsou povoleny pro implementaci operaci.  
  
4.  Klikněte na tlačítko **OK** a **ReceiveActivity** aktivity se zobrazí název operace pro operaci, která implementuje.  
  
5.  Aktivity pracovního postupu, který chcete použít k provedení této operace v rámci umístit **ReceiveActivity** aktivity.  
  
## <a name="see-also"></a>Viz také  
 [Výběr dialogové okno operace (zastaralé)](../workflow-designer/choose-operation-dialog-box-legacy.md)   
 [Postupy: volání operaci kontraktu WCF (zastaralé)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)