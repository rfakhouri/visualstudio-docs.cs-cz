---
title: Data třídy dědičnosti (O R Designer) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: af32653c-f4e6-4217-8c5a-e32b322b4918
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f2c1f5328abd8ea814e1175b17129dd8a89040ef
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697938"
---
# <a name="data-class-inheritance-or-designer"></a>Dědičnost datových tříd (Návrhář O/R)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Jiné objekty, jako jsou [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] dědičnost lze použít třídy a být odvozen od jiných tříd. V kódu můžete zadat dědičnosti relací mezi objekty deklarací, že jedna třída dědí z jiné. V databázi vztahy dědičnosti vytvoří několika způsoby. [!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]) Podporují koncept dědičnosti jedné tabulky, jak často je implementován v relačních systémech.  
  
 V dědičnosti jedné tabulky je izolované databáze tabulku, která obsahuje sloupce pro základní a odvozené třídy. S relačními daty rozlišující sloupec obsahuje hodnotu, která určuje, které třídě daný záznam patří. Představte si třeba osoby tabulku, která obsahuje všechny uživatele náhradník společnosti. Někteří lidé jsou zaměstnanci a někteří lidé jsou správci. Osoby tabulka obsahuje sloupec s názvem typu, který má hodnotu 1 pro manažery a hodnota 2 pro zaměstnance. Typ sloupec je sloupec diskriminátoru. V tomto scénáři můžete vytvořit podtřídu zaměstnanců a naplnit třída se pouze záznamy, které mají hodnotu typu 2.  
  
 Při konfiguraci dědičnosti tříd entit pomocí [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], přetáhněte jednu tabulku, která obsahuje data dědičnosti na Návrhář dvakrát: jednou pro každou třídu v hierarchii dědičnosti. Po přidání tabulky do návrháře spojujeme je s dědičnosti položky z **Návrhář relací objektů** nástrojů a pak nastavit čtyři vlastnosti dědičnosti v **vlastnosti** okna.  
  
## <a name="inheritance-properties"></a>Dědičnost vlastnosti  
 V následující tabulce jsou uvedeny dědičnosti vlastností a jejich popis:  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|Vlastnost diskriminátoru|Vlastnost (mapována na sloupec), která určuje, která třída aktuální záznam patří.|  
|Hodnota diskriminátoru základní třídy|Hodnota (v sloupec označený jako vlastnost diskriminátoru), která určuje, že záznam je základní třídy.|  
|Hodnota diskriminátor odvozené třídy|Hodnota (ve vlastnosti určené jako vlastnost diskriminátoru), která určuje, že záznam je odvozené třídy.|  
|Výchozí hodnota dědičnosti|Třída, která by měla být naplněn, pokud hodnota ve vlastnosti určené jako **vlastnost diskriminátoru** neodpovídá buď **hodnota diskriminátoru základní třídy** nebo **odvozených tříd Hodnota diskriminátoru**.|  
  
 Vytvoření objektu modelu, který používá dědičnosti a odpovídá na relační data, může být trochu matoucí. Toto téma obsahuje informace o základních konceptech a jednotlivé vlastnosti, které jsou potřeba ke konfiguraci dědičnosti. Následující témata obsahují jasnější vysvětlení, jak nakonfigurovat dědičnosti s [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
|Téma|Popis|  
|-----------|-----------------|  
|[Postupy: Konfigurace dědičnosti pomocí Návrháře relací objektů](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)|Popisuje postup konfigurace tříd entit, které používají jedné tabulky dědičnosti pomocí [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].|  
|[Návod: Vytvoření tříd LINQ to SQL pomocí dědičnosti jedné tabulky (Návrhář relací objektů)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)|Obsahuje podrobné pokyny o tom, jak nakonfigurovat tříd entit, které používají jedné tabulky dědičnosti pomocí [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].|  
  
## <a name="see-also"></a>Viz také  
 [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [Návod: Vytvoření třídy LINQ to SQL (Návrhář O-R)](https://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [Návod: Vytvoření třídy LINQ to SQL s použitím dědičnosti jedné tabulky (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)   
 [Začínáme](https://msdn.microsoft.com/library/db8a557a-fef8-4f4f-bb91-8cff7250ee25)
