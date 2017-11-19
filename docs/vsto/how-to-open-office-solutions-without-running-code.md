---
title: "Postupy: otevření řešení pro systém Office bez spuštění kódu | Microsoft Docs"
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
- Office solutions [Office development in Visual Studio], opening
- opening Office solutions
- bypassing assemblies
- solutions [Office development in Visual Studio], opening
- assemblies [Office development in Visual Studio], bypassing
- Office documents [Office development in Visual Studio, opening without running code
- documents [Office development in Visual Studio], opening without running code
ms.assetid: a853d91c-9fd6-421a-b3a2-956b6b494b96
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 74cc162e0323656bea9d48c8458eaf77519fdc14
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Manifestů aplikace a nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md)  
  
  