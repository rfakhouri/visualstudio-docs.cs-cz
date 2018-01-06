---
title: "Výběr dialogové okno operace (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Workflow.Activities.Design.OperationPickerDialog.UI
ms.assetid: bc3ec902-7797-494e-af48-e70c97eb6779
caps.latest.revision: "10"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 2db745d34c86e4b0aa5639872106096421044bce
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="choose-operation-dialog-box-legacy"></a>Výběr dialogové okno operace (zastaralé)
Toto téma popisuje, jak používat **zvolte operaci** dialogovém okně pro starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 **Zvolte operaci** dialogové okno slouží k výběru operace přidružení <xref:System.Workflow.Activities.ReceiveActivity> aktivity nebo <xref:System.Workflow.Activities.SendActivity> aktivity. Další informace o použití tohoto dialogového okna s těmito aktivitami najdete v tématu [postupy: implementace kontraktu operace s WCF (zastaralé)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md) a [postup: vyvolání operaci kontraktu WCF (zastaralé)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md).  
  
 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **zvolte operaci** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**Přidat smlouvy**|Vytvoří nové smlouvy. Můžete definovat nových operací v této smlouvě. (Používá se s <xref:System.Workflow.Activities.ReceiveActivity> pouze.)|  
|**Operace přidání**|Přidá do nové smlouvy, kterou jste vytvořili v nových operací **zvolte operaci** dialogové okno. **Poznámka:** nových operací můžete přidat pouze na smlouvy, které jste vytvořili pomocí **zvolte operaci** dialogové okno. <br /><br /> (Používá se s <xref:System.Workflow.Activities.ReceiveActivity> pouze.)|  
|**Importujte...**|Importuje dříve definovaném kontraktu a umožňuje vybrat operace z této smlouvy.|  
|**Název operace**|Název aktuálně vybranou operaci. Toto pole je k dispozici pro úpravy pouze v případě, že jste vytvořili operace prostřednictvím **zvolte operaci** dialogové okno.|  
|**Parametry**|Karta obsahující definice parametr pro aktuálně vybranou operaci. **Poznámka:** definicemi parametrů lze změnit pouze v případě, že jste vytvořili operace prostřednictvím **zvolte operaci** dialogové okno.|  
|**Vlastnosti**|Karta obsahující <xref:System.Net.Security.ProtectionLevel> nastavení pro zprávy odeslané mezi klientem a službou. **Poznámka:** na této kartě je povoleno pouze v případě, že jste vytvořili operace prostřednictvím **zvolte operaci** dialogové okno.|  
|**Oprávnění**|Karta obsahující <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionName%2A> a <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionRole%2A> vlastnosti uživatelů, kteří mají povoleno volat tuto operaci. Například pokud pouze uživatelé ze skupiny správců měla povoleno volat tuto operaci, pak by napíšete "Administrators" **Role** textové pole.<br /><br /> Na této kartě je povolen pro obě operace vytvořena prostřednictvím **ChooseOperation** dialogové okno a operací, které byly importovány pomocí **Import** tlačítko.|  
  
> [!NOTE]
>  **Zvolte operaci** dialogové okno zobrazí pouze smluv nebo operace, které jsou používány jiné <xref:System.Workflow.Activities.SendActivity> aktivitám v pracovním postupu. Podobně **zvolte operaci** dialogové okno pro <xref:System.Workflow.Activities.ReceiveActivity> aktivity se zobrazuje pouze kontrakty nebo operace, které jsou používány jiné **ReceiveActivity** aktivitám v pracovním postupu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: implementace kontraktu operace s WCF (zastaralé)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Postupy: volání operaci kontraktu WCF (zastaralé)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Nápověda k uživatelskému rozhraní návrháře pro programovací model Windows Workflow Foundation](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)