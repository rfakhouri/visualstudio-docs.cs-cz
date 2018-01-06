---
title: "Návod: LinqToXmlDataBinding příklad | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aedf42e8-896c-48fa-88df-7f7c9536aa69
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bc78fd4331839ce1a55253a719c40f8b19dea491
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-linqtoxmldatabinding-example"></a>Návod: LinqToXmlDataBinding příklad
Tento návod popisuje příklad LinqToXmlDataBinding a vysvětluje některé zajímavějšího obsah jeho dvě primární zdrojové soubory, L2DBForm.xaml a L2DBForm.xaml.cs.  
  
## <a name="prerequisites"></a>Požadavky  
 Předtím, než se pustíte do čtení tohoto návodu, důrazně doporučujeme vytvořit a spustit LinqToXmlDataBinding program, jak je popsáno v [postupy: sestavení a spuštění ukázkového LinqToXmlDataBinding](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md).  
  
## <a name="remarks"></a>Poznámky  
 LinqToXmlDataBinding program je Windows Presentation Foundation (WPF) aplikace, která se skládá z jazyka C# a zdrojových souborů XAML. Obsahuje vložené dokument XML, který definuje seznam seznamů a umožňuje uživatelům zobrazit, přidat, odstranit a upravit tyto položky. Skládá se z následujících dvou souborech primární zdroj:  
  
-   L2DBForm.XAML obsahuje kód XAML deklarace pro uživatelské rozhraní (UI) hlavního okna. Obsahuje taky oddíl okno prostředek, který definuje zprostředkovatele dat a embedded dokumentu XML pro výpis adresáře.  
  
-   L2DBForm.XAML.cs obsahuje inicializace a obslužné metody událostí související s uživatelským rozhraním.  
  
 Hlavní okno je rozdělené do následujících čtyř svislé částí uživatelského rozhraní:  
  
-   **XML** zobrazí nezpracované XML zdroj seznam vložených adresáře.  
  
-   **Sešit seznamu** zobrazí jako standardní text položky seznamu a umožňuje uživateli vybrat a odstranění jednotlivých položek.  
  
-   **Upravit vybranou knihu** umožňuje uživateli upravit hodnoty přidružené k položku v aktuálně vybraném seznamu.  
  
-   **Přidat nový adresář** vytvořit novou položku seznamu, na základě hodnot zadaných uživatelem.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Téma|Popis|  
|-----------|-----------------|  
|[Zdrojový kód L2DBForm.xaml](../designers/l2dbform-xaml-source-code.md)|Obsahuje obsah a popis kódu XAML v souboru L2DBForm.xaml.|  
|[Zdrojový kód L2DBForm.xaml.cs](../designers/l2dbform-xaml-cs-source-code.md)|Obsahuje obsah a popis C# zdrojový kód v souboru L2DBForm.xaml.cs.|  
  
## <a name="see-also"></a>Viz také  
 [Datové vazby WPF pomocí LINQ to XML příklad](../designers/wpf-data-binding-using-linq-to-xml-example.md)   
 [Postupy: Sestavení a spuštění příkladu LinqToXmlDataBinding](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md)