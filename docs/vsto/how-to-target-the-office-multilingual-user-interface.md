---
title: "Postupy: cíle vícejazyčné uživatelské rozhraní Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- globalization [Office development in Visual Studio], user interface targeting
- MUI [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], localization
- Multilingual User Interface [Office development in Visual Studio]
- localization [Office development in Visual Studio], user interface targeting
- Office applications [Office development in Visual Studio], globalization
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 39ee8b6bdcb4ad647164ec555cfa37ee9cfe8f50
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-target-the-office-multilingual-user-interface"></a>Postupy: Cílení na vícejazyčné uživatelské rozhraní systému Office
  Multilingual User Interface (MUI) je funkce Microsoft Office, která dává možnost ke změně jazyka uživatelského rozhraní (UI) koncového uživatele. Koncový uživatel práce s anglickou uživatelského rozhraní můžete například změnit jazyk uživatelského rozhraní na španělština.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Pokud vaše aplikace bude používat uživatelé, kteří používají více jazyků systému Office, můžete přidat kód, který automaticky změní jazyk řetězců uživatelského rozhraní s jazykem používá Office na počítači uživatele (Pokud má uživatel správnou prostředky nainstalovaná).  
  
### <a name="to-check-the-current-office-ui-setting"></a>Chcete-li zkontrolovat aktuální nastavení uživatelského rozhraní sady Office  
  
1.  Použití <xref:System.Threading.Thread.CurrentUICulture%2A> vlastnost aktuálního vlákna. Nastavení jazyka řetězců uživatelského rozhraní s jazykem používá verzi systému Office, které jsou aktuálně spuštěné v počítači uživatele.  
  
     [!code-vb[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#10)]
     [!code-csharp[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#10)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: cílení na aplikace Office prostřednictvím primární spolupráce – sestavení](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md)  
  
  