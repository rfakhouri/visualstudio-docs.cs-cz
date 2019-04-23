---
title: 'Postupy: Otevření řešení pro systém Office bez spuštění kódu'
ms.date: 02/02/2017
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9b9a88aff9cd587f695ace56c44eaf9c8fcb8875
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60117197"
---
# <a name="how-to-open-office-solutions-without-running-code"></a>Postupy: Otevření řešení pro systém Office bez spuštění kódu
  Řešení Microsoft Office vytvořené pomocí rozšíření spravovaného kódu spustí i v případě, že nastavení zabezpečení aplikace Office koncového uživatele je nastavena na hodnotu Vysoká. Je to proto, že spravuje zabezpečení kódu .NET sestavení rozhraní Microsoft .NET Framework, ne společnost Microsoft Office.

 Existují však časy, kdy můžete chtít otevřít dokument bez spuštění kódu. Například kód, který běží po otevření dokumentu může změnit obsah, ale chcete aktualizovat dokument vzhled před změnami v kódu. Nebo můžete chtít odeslat dokument se některé informace v ní někdo a nechcete, aby kód ke spuštění a případně změnit obsah.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Existuje několik způsobů, jak otevřít dokument nebo sešit, který obsahuje rozšíření spravovaného kódu bez spuštění kódu sestavení.

## <a name="to-bypass-the-assembly-by-using-the-shift-key"></a>Obejít sestavení pomocí klávesy Shift

- Otevřít dokumenty a sešity **souboru** nabídky při podržení **Shift** klíč zabránit vyvolávání událostí inicializace při otevírání dokumentů aplikace Word a Excel.

    > [!NOTE]
    >  Pokud otevřete dokumentu nebo sešitu z **Začínáme** podokna úloh, podržte **Shift** nepoužívat kód. Navíc podržíte stisknutou klávesu SHIFT nebrání událostí vyvolaných po otevření dokumentu.

     Tato metoda je užitečná, pokud chcete otevřít dokument provádět změny bez kódu, spouštění a nejprve změny dokumentu.

## <a name="to-bypass-an-assembly-by-renaming-or-removing-it"></a>Obejít sestavení tak, přejmenování nebo neodebrali.

- Pokud máte potřebná oprávnění na počítači, kde je umístěné sestavení, můžete přejmenovat nebo odebrat sestavení, aby dokumentem nebo sešitem, nejde ho najít. Výsledkem je chyba se vyvolá při každém otevření dokumentu Office.

     Pokud řešení používá více lidí, tato metoda řešení zabraňuje spuštění pro všechny z nich. To může být užitečné, pokud je nalezen problém v kódu nebo odkazovaného serveru a zabráníte všem uživatelům, ale jeho spuštění.

## <a name="see-also"></a>Viz také:
- [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)
- [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)
- [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)
- [Manifesty aplikace a nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md)
