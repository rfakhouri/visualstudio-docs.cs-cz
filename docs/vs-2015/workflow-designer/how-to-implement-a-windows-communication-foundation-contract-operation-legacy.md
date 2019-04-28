---
title: 'Postupy: Implementace Windows Communication Foundation smlouvy operaci (starší verze) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: d6aeb20e-fac8-4a9d-bd26-ae78bef96b41
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 56866e084eac7dc3a3ac2a0b80baaa2533ccd285
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62931184"
---
# <a name="how-to-implement-a-windows-communication-foundation-contract-operation-legacy"></a>Postupy: Implementace operace kontraktu technologie Windows Communication Foundation (starší verze)
Toto téma popisuje, jak implementovat [!INCLUDE[indigo1](../includes/indigo1-md.md)] smlouvy operace pomocí starší verze [!INCLUDE[wfd1](../includes/wfd1-md.md)] , který cílí [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Po přetažení **ReceiveActivity** aktivitu z panelu nástrojů na plochu návrháře pracovního postupu buď vytvoříte nový [!INCLUDE[indigo2](../includes/indigo2-md.md)] smlouvy nebo importovat existující kontrakt a implementaci operace. Vyberte nebo vytvořte vaše smlouva a jeho operace, ať už [zvolte operaci dialogové okno (starší verze)](../workflow-designer/choose-operation-dialog-box-legacy.md).  
  
### <a name="to-implement-a-wcf-contract-operation"></a>Implementace operace kontraktu WCF  
  
1. Dvakrát klikněte **ReceiveActivity** aktivity v Návrháři nebo klikněte na tři tečky vedle položky **ServiceOperationInfo** vlastnost v **vlastnosti** podokně.  
  
2. Proveďte jednu z těchto akcí:  
  
   - Klikněte na tlačítko **přidat smlouvy** v pravém horním rohu dialogového okna. Tím se vytvoří nový [!INCLUDE[indigo2](../includes/indigo2-md.md)] kontrakt a operace pro vás.  
  
      -nebo-  
  
   - Klikněte na tlačítko **Import** v pravém horním rohu dialogového okna. [Procházet a vybrat typ dialogovému oknu rozhraní .NET (starší verze)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) otevře. Vyhledejte sestavení nebo projekt, který obsahuje kontrakt, který chcete. Zvolte smlouvu a klikněte na tlačítko **OK**.  
  
     Po vytvoření nebo importovat kontrakt, můžete přidat nové operace s touto smlouvou importované nebo vytvořené. Pokud chcete přidat novou operaci, zvolte smlouvu a klikněte na tlačítko **přidat operaci** v pravém horním rohu dialogového okna. Po dokončení operace přidávání, pokračujte krokem 3.  
  
3. Vyberte operaci, kterou chcete přidružit **ReceiveActivity** aktivity. Definice operace můžete upravit tak, že změníte název operace, parametry, vlastnosti a nastavení oprávnění.  
  
    Chcete-li změnit název, zadejte nový název do **název operace** textového pole.  
  
    Klikněte na tlačítko **parametry** kartu pro přístup k parametrů operace zobrazíte. Můžete změnit název, typ nebo směr parametru a přidání nebo odstranění parametrů operace.  
  
    Klikněte na tlačítko **vlastnosti** kartu pro přístup k funkcím operace ochrany úrovně a podporovaných zpráv exchange operace.  
  
    Klikněte na tlačítko **oprávnění** kartu k určení, které skupiny můžou implementovat operace.  
  
4. Klikněte na tlačítko **OK** a **ReceiveActivity** aktivity se zobrazí název operace pro operace, která implementuje.  
  
5. Umístit aktivity pracovního postupu, který se chystáte použít k provedení této operace v rámci **ReceiveActivity** aktivity.  
  
## <a name="see-also"></a>Viz také  
 [Zvolte dialogové okno operaci (starší verze)](../workflow-designer/choose-operation-dialog-box-legacy.md)   
 [Postupy: Vyvolání operace kontraktu WCF (starší verze)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)