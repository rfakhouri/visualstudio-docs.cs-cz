---
title: Zvolte dialogové okno operaci (starší verze) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Design.OperationPickerDialog.UI
ms.assetid: bc3ec902-7797-494e-af48-e70c97eb6779
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7b9d40f3627cd24aa7758a0d599eb6e5d770c9f8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54756777"
---
# <a name="choose-operation-dialog-box-legacy"></a>Dialogové okno Zvolit operaci (starší verze)
Toto téma popisuje, jak používat **zvolte operaci** dialogové okno v starší [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Použijte starší [!INCLUDE[wfd2](../includes/wfd2-md.md)] potřeba cílit na platformu [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 **Zvolte operaci** dialogové okno se používá pro výběr operace přidružení <xref:System.Workflow.Activities.ReceiveActivity> aktivity nebo <xref:System.Workflow.Activities.SendActivity> aktivity. Další informace o používání toto dialogové okno s těmito aktivitami v tématu [jak: Implementace operace kontraktu WCF (starší verze)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md) a [jak: Vyvolání operace kontraktu WCF (starší verze)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md).  
  
 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **zvolte operace** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**Přidat smlouvy**|Vytvoří nové smlouvy. Můžete definovat nové operace v této smlouvě. (Používá se s <xref:System.Workflow.Activities.ReceiveActivity> pouze.)|  
|**Operace přidání**|Přidá nové operace do nové smlouvy, které jste vytvořili **zvolte operace** dialogové okno. **Poznámka:**  Můžete přidat nové operace pouze na vytvoříte prostřednictvím smlouvy **zvolte operace** dialogové okno. <br /><br /> (Používá se s <xref:System.Workflow.Activities.ReceiveActivity> pouze.)|  
|**Import...**|Importuje dříve definovanou smlouvu a umožňuje vybrat operace z této smlouvy.|  
|**Název operace**|Název aktuálně vybranou operaci. Je k dispozici pro úpravy pouze v případě, že jste vytvořili operaci prostřednictvím tohoto textového pole **zvolte operace** dialogové okno.|  
|**Parametry**|Karta obsahující definice parametru pro aktuálně vybranou operaci. **Poznámka:**  Parametr definice lze změnit pouze v případě, že jste vytvořili operaci prostřednictvím **zvolte operace** dialogové okno.|  
|**Vlastnosti**|Karta obsahující <xref:System.Net.Security.ProtectionLevel> nastavení pro zprávy odeslané mezi klientem a službou. **Poznámka:**  Na této kartě je povolená jenom v případě, že jste vytvořili operaci prostřednictvím **zvolte operace** dialogové okno.|  
|**Oprávnění**|Karta obsahující <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionName%2A> a <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionRole%2A> vlastnosti uživatele, kteří jsou povoleny pro volání této operace. Například pokud pouze uživatelé ze skupiny Administrators se může volat tuto operaci, pak by napíšete "Administrators" **Role** textového pole.<br /><br /> Na této kartě je povolen pro obě operace vytvořených prostřednictvím **ChooseOperation** dialogové okno a operace, jež byla importována pomocí **Import** tlačítko.|  
  
> [!NOTE]
>  **Zvolte operaci** dialogové okno zobrazí pouze smluv nebo operací, které používají jiné <xref:System.Workflow.Activities.SendActivity> aktivitám v pracovním postupu. Podobně **zvolte operaci** dialogové okno pro <xref:System.Workflow.Activities.ReceiveActivity> aktivity se zobrazí pouze smluv nebo operací, které používají jiné **ReceiveActivity** aktivitám v pracovním postupu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Implementace operace kontraktu WCF (starší verze)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Postupy: Vyvolání operace kontraktu WCF (starší verze)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Nápověda k uživatelskému rozhraní návrháře pro programovací model Windows Workflow Foundation](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)