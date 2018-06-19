---
title: 'Postupy: Office cíl aplikací prostřednictvím primární spolupráce – sestavení'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- assemblies [Office development in Visual Studio], PIA references
- primary interop assemblies [Office development in Visual Studio], adding references to
- Office primary interop assemblies in Visual Studio, adding references to
- Office applications [Office development in Visual Studio], automating
- application development [Office development in Visual Studio], automating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 32ff157e3986836ac13472c4a9ed8a7b01f06e04
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
ms.locfileid: "34262509"
---
# <a name="how-to-target-office-applications-through-primary-interop-assemblies"></a>Postupy: Office cíl aplikací prostřednictvím primární spolupráce – sestavení
  Když vytvoříte nový projekt Office, Visual Studio automaticky přidá odkazy na aplikace Microsoft Office primární spolupracující sestavení (PIA) požadovaná pro sestavení projektu. Odkazy na další PIA musíte přidat v následujících scénářích:  
  
-   Chcete používat funkce jiné aplikace Microsoft Office ve vašem projektu. Například můžete chtít používat funkce aplikace Microsoft Office Excel v projektu pro aplikaci Microsoft Office Word.  
  
-   Chcete automatizovat aplikace Microsoft Office, které nemají vyhrazené projekty v sadě Visual Studio, jako je například Microsoft Office Access.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="to-add-a-reference-to-a-primary-interop-assembly"></a>Chcete-li přidat odkaz na primární spolupracující sestavení  
  
1.  Otevřete Office projekt a vyberte název projektu v **Průzkumníku řešení**.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat odkaz na**.  
  
3.  Na **Framework** vyberte PIA – chcete v **název komponenty** seznamu. Další informace o dostupných primární spolupracující sestavení aplikace Microsoft Office, najdete v části [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md).  
  
     Pokud cíle projektu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, **vložit zprostředkovatel komunikace s objekty typy** pro odkaz na sestavení je nastavena na **True** ve výchozím nastavení. Pomocí tohoto nastavení řešení nevyžaduje PIA na počítačích koncových uživatelů. Další informace najdete v tématu [návrhu a vytvářet řešení systému Office](../vsto/designing-and-creating-office-solutions.md).  
  
    > [!NOTE]  
    >  V projektech Office vždy přidáte odkazy na PIA Office s použitím **.NET** kartě **přidat odkaz na** dialogové okno místo **COM** kartě. Další informace najdete v tématu [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md).  
  
4.  Click **OK**.  
  
     Název sestavení se zobrazí v **odkazy** složky **Průzkumníku řešení**.  
  
## <a name="see-also"></a>Viz také  
 [Primární spolupracující sestavení sady Office](../vsto/office-primary-interop-assemblies.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Postupy: Primární spolupracující sestavení Office instalace](../vsto/how-to-install-office-primary-interop-assemblies.md)  
  
  