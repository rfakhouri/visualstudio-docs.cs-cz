---
title: 'Chyba: závislost &#39;souboru&#39; v projektu &#39;projektu&#39; nelze zkopírovat do běhového adresáře, protože by vznikl konflikt se závislostí &#39;souboru&#39; | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
f1_keywords:
- vs.tasklisterror.copy_version_conflict
ms.assetid: cd7de1eb-7d58-4e2c-9811-a7201f7817be
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7726d615c3495845ffdf73d69ffc7d8fae155272
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65688277"
---
# <a name="error-the-dependency-39file39-in-project-39project39-cannot-be-copied-to-the-run-directory-because-it-would-conflict-with-dependency-39file39"></a>Chyba: závislost &#39;souboru&#39; v projektu &#39;projektu&#39; nelze zkopírovat do běhového adresáře, protože by vznikl konflikt se závislostí &#39;souboru&#39;
Dojde ke konfliktu mezi; více různých závislostí se stejným názvem soubor je zkopírován do adresáře bin pro spuštění aplikace. Běhového adresáře nemůže konflikt vyřešit, protože žádný z závislosti primární odkazy.  
  
 Tato chyba způsobí, že sestavení selže.  
  
 Tuto položku seznamu úkolů dvojitým kliknutím přejdete na uzel odkazy projektu, ve kterém dochází ke konfliktu.  
  
 **Chcete-li opravit tuto chybu**  
  
- Vytvořit sestavení přímý odkaz na svůj projekt. Je to možné nevýhodou tohoto přístupu je, že sestavení, ve kterém můžete zvolit není zaručeno, že pro práci s sestavení, které vyžadují jiná verze odkazovaného sestavení.  
  
     \- nebo –  
  
- Ujistěte se, že obě kopie sestavení se silným názvem a v globální mezipaměti sestavení. Tím se eliminuje potřeba kopírovat sestavení do adresáře bin.  
  
## <a name="see-also"></a>Viz také  
 [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)   
 [Globální mezipaměť sestavení](https://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202)   
 [Sestavení se silným názvem](https://msdn.microsoft.com/library/d4a80263-f3e0-4d81-9b61-f0cbeae3797b)   
 [Správa verzí sestavení](https://msdn.microsoft.com/library/775ad4fb-914f-453c-98ef-ce1089b6f903)   
 [Postupy: Vytváření a odebírání závislostí projektu](../ide/how-to-create-and-remove-project-dependencies.md)