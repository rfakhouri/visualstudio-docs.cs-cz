---
title: 'Postupy: Cílení na vícejazyčné uživatelské rozhraní sady Office'
ms.date: 02/02/2017
ms.topic: conceptual
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c495f8a83b58c53404056befd2227b295c3324d5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62961136"
---
# <a name="how-to-target-the-office-multilingual-user-interface"></a>Postupy: Cílení na vícejazyčné uživatelské rozhraní sady Office
  Multilingual User Interface (MUI) je funkce aplikace Microsoft Office, poskytující koncovému uživateli možnost měnit jazyk uživatelského rozhraní (UI). Práce s anglickou uživatelského rozhraní koncového uživatele můžete například změnit jazyk uživatelského rozhraní na španělštinu.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 Pokud vaše aplikace bude používat uživatelé, kteří používají řadu jazyků sady Office, můžete přidat kód, který automaticky změní jazyk vašeho řetězce uživatelského rozhraní tak, aby odpovídaly jazyk používá Office na počítači uživatele (Pokud je nainstalované správné prostředky má uživatel).

## <a name="to-check-the-current-office-ui-setting"></a>Pokud chcete zkontrolovat aktuální nastavení uživatelského rozhraní sady Office

1. Použití <xref:System.Threading.Thread.CurrentUICulture%2A> vlastnost aktuálního vlákna. Nastavte jazyk vašeho řetězce uživatelského rozhraní tak, aby odpovídaly jazyk používá verzi systému Office, který aktuálně běží na počítači uživatele.

     [!code-vb[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#10)]
     [!code-csharp[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#10)]

## <a name="see-also"></a>Viz také:
- [Postupy: Cílení na aplikace Office primárních sestaveních vzájemné spolupráce](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)
- [Pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md)
