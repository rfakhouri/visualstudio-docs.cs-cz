---
title: 'Postupy: otevření řešení pro systém Office bez spuštění kódu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office solutions [Office development in Visual Studio], opening
- opening Office solutions
- bypassing assemblies
- solutions [Office development in Visual Studio], opening
- assemblies [Office development in Visual Studio], bypassing
- Office documents [Office development in Visual Studio, opening without running code
- documents [Office development in Visual Studio], opening without running code
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 86a44d2a6c82f65d91c558c76743a8fbbd2fa1e8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-open-office-solutions-without-running-code"></a>Postupy: Otevření řešení pro systém Office bez spuštění kódu
  Řešení Microsoft Office vytvořené pomocí rozšíření spravovaného kódu se spustí i v případě nastavení zabezpečení v aplikaci Office koncového uživatele je nastavena na hodnotu Vysoká. Je to proto, že zabezpečení kódu sestavení .NET je spravovaná rozhraní Microsoft .NET Framework, nikoliv společností Microsoft Office.  
  
 Existují však situace když budete chtít otevřít dokument, bez spuštění kódu. Například kód, který běží po otevření dokumentu může změnit obsah, ale chcete aktualizovat dokument vzhled před změny kódu. Nebo můžete chtít poslat dokument s určité informace v ní někdo a nechcete, aby kód ke spuštění a případně změnit obsah.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Existuje několik způsobů otevřete dokument nebo sešit, který obsahuje rozšíření spravovaného kódu bez spuštění kódu sestavení.  
  
### <a name="to-bypass-the-assembly-by-using-the-shift-key"></a>Pomocí klávesy SHIFT obejít sestavení  
  
-   Otevřít dokumenty a sešity z **souboru** nabídky při podržíte stisknutou klávesu SHIFT a zabránit vyvolání inicializace událostí, když je otevření dokumentu Word a Excel.  
  
    > [!NOTE]  
    >  Pokud otevřete dokument nebo sešitu z **Začínáme** podokna úloh podržíte stisknutou klávesu SHIFT není vynechat kód. Navíc podržíte stisknutou klávesu SHIFT nezabrání událostí vyvolaných po otevření dokumentu.  
  
     Tato metoda je užitečná, pokud chcete otevřít dokument měnit, aniž by kód spuštěný a nejprve změny dokumentu.  
  
### <a name="to-bypass-an-assembly-by-renaming-or-removing-it"></a>Obejít sestavení a přejmenování nebo odebráním  
  
-   Pokud máte na počítači, kde se nachází sestavení potřebná oprávnění, můžete přejmenovat nebo odebrat sestavení, dokumentu nebo sešitu ji nemůže najít. To vede k chybě vyvolaných pokaždé, když je otevřen dokumentu systému Office.  
  
     Pokud řešení používá více uživatelů, tato metoda řešení zabraňuje spuštění pro každou z nich. To může být užitečné, pokud je zjištěn problém v kódu nebo odkazovaného serveru a chcete zastavit všechny uživatele od její provedení.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Manifesty aplikací a nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md)  
  
  