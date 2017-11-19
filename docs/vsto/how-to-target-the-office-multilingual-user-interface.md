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
ms.assetid: b1f03164-f0cf-42e3-942b-8cf90c242ffb
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3ee88cbcde2a25a13b4c4432afe5a5b1397ab727
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md)  
  
  