---
title: "Přehled modelu objektů aplikace Visio | Microsoft Docs"
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
- Visio [Office development in Visual Studio], object model
- object models [Office development in Visual Studio], Office
- object models [Office development in Visual Studio], Visio
- objects [Office development in Visual Studio], Office object models
- Office object models
- Visio object model
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e829842f4e530b014a19f69c567a91dc49bd78e6
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="visio-object-model-overview"></a>Přehled modelu objektů aplikace Visio
  K vývoji řešení pro systém Office pro aplikaci Microsoft Office Visio, můžete pracovat s Visio – objektový model. Tento objektový model se skládá z třídy a rozhraní, které jsou uvedeny v primární spolupracující sestavení pro aplikaci Visio a jsou definovány v oboru názvů Microsoft.Office.Interop.Visio.  
  
 Toto téma obsahuje stručný přehled modelu objektů aplikace Visio. Informace o používání Visio – objektový model k provádění úloh v projektech Office najdete v následujících tématech:  
  
-   [Práce s dokumenty aplikace Visio](../vsto/working-with-visio-documents.md)  
  
-   [Práce s obrazci aplikace Visio](../vsto/working-with-visio-shapes.md)  
  
## <a name="understanding-the-visio-object-model"></a>Vysvětlení modelu objektů aplikace Visio  
 Visio poskytuje mnoho objektů, se kterými můžete pracovat. Tyto objekty jsou uspořádány do hierarchie, která přesně dodržuje uživatelské rozhraní. V horní části hierarchie [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx) objektu. Tento objekt představuje aktuální instanci aplikace Visio. Objekt Microsoft.Office.Interop.Visio.Application obsahuje objekty Microsoft.Office.Interop.Visio.Document a Microsoft.Office.Interop.Visio.Page, jakož i Microsoft.Office.Interop.Visio.Documents a Microsoft.Office.Interop.Visio.Pages kolekce. Každá z těchto objektů a kolekcí má mnoho metody a vlastnosti, které můžete přístup k manipulaci a pracovat s ním.  
  
 Další informace najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx), [Microsoft.Office.Interop.Visio.Document](https://msdn.microsoft.com/library/office/ff765575.aspx), a [ Microsoft.Office.Interop.Visio.Page](https://msdn.microsoft.com/library/office/ff767035.aspx) objekty a také [Microsoft.Office.Interop.Visio.Documents](https://msdn.microsoft.com/library/office/ff768812.aspx) a [Microsoft.Office.Interop.Visio.Pages](https://msdn.microsoft.com/library/office/ff766165.aspx) kolekce.  
  
 Následující části popisují stručně nejvyšší úrovně objekty a jejich vzájemné interakce mezi sebou. Tyto objekty zahrnují následující objekty:  
  
-   objekt aplikace  
  
-   Objekt dokumentu  
  
-   objekt stránky  
  
### <a name="application-object"></a>Objekt aplikace  
 Objekt Microsoft.Office.Interop.Visio.Application představuje aplikace Visio a je nadřazeného všechny ostatní objekty. Její členy použije obvykle do aplikace Visio jako celek. Vlastnosti a metody Microsoft.Office.Interop.Visio.Application a Microsoft.Office.Interop.Visio.ApplicationSettings objekty, které můžete použít k řízení prostředí aplikace Visio.  
  
 V doplňku VSTO projekty, můžete přístup k objektu Microsoft.Office.Interop.Visio.Application pomocí `Application` pole z `ThisAddIn` třídy. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
### <a name="document-object"></a>Objekt dokumentu  
 Objekt Microsoft.Office.Interop.Visio.Document je důležitá pro programování Visio. Reprezentuje kreslení, vzorníku nebo souboru šablony. Při otevírání dokumentů aplikace Visio nebo vytvořit nový dokument, můžete vytvořit nový objekt Microsoft.Office.Interop.Visio.Document, která se přidá do kolekce Microsoft.Office.Interop.Visio.Documents Microsoft.Office.Interop.Visio.Application objektu .  
  
 Dokument, který je vybrán se nazývá aktivní dokument. Je zobrazena ve vlastnosti Microsoft.Office.Interop.Visio.Application.ActiveDocument Microsoft.Office.Interop.Visio.Application objektu.  
  
### <a name="page-object"></a>Objekt stránky  
 Objekt Microsoft.Office.Interop.Visio.Page představuje oblasti výkresu stránku popředí nebo na pozadí. Vlastnost Microsoft.Office.Interop.Visio.Page.Background můžete určit, zda je na stránce popředí nebo pozadí stránky.  
  
 Pokud chcete vytvořit tvarů, můžete použít metody, které zahrnují metody Microsoft.Office.Interop.Visio.Page.DrawSpline a Microsoft.Office.Interop.Visio.Page.DrawOval. Kromě toho můžete načíst hlavních serverů ze vzorníků a umístit obrazce na stránku pomocí metody Microsoft.Office.Interop.Visio.Page.Drop nebo Microsoft.Office.Interop.Visio.Page.DropMany.  
  
## <a name="using-the-visio-object-model-documentation"></a>Pomocí dokumentace modelu objektů aplikace Visio  
 Úplné informace o modelu objektů aplikace Visio najdete odkaz na aplikaci Visio VBA modelu. Reference objektu modelu VBA dokumentů Visio – objektový model, jako je zpřístupněné pro Visual Basic pro aplikace (VBA) kód. Další informace najdete v tématu [odkaz na objekt modelu aplikace Visio 2010](http://go.microsoft.com/fwlink/?LinkId=199775).  
  
 Všechny objekty a členy ve model odkaz na VBA odpovídají typy a členy v primární spolupracující sestavení aplikace Visio (PIA –). Například objektu dokumentu ve model odkaz na VBA odpovídá typu Microsoft.Office.Interop.Visio.Document v PIA aplikace Visio. I když reference VBA objektu modelu poskytuje příklady kódu pro většinu vlastností, metod a událostí, pokud chcete používat v projektu doplňku Visio VSTO, který vytvoříte pomocí Visual musí překládat VBA kód v této referenci na Visual Basic a Visual C# Studio.  
  
> [!NOTE]  
>  V tuto chvíli není žádná referenční dokumentace pro primární spolupracující sestavení aplikace Visio.  
  
 Ukázky související kódu a další nástroje pro vytváření řešení pro aplikaci Visio najdete v tématu [Visio 2010 Software Development Kit](http://go.microsoft.com/fwlink/?LinkId=196501).  
  
### <a name="additional-types-in-primary-interop-assemblies"></a>Další typy v primární spolupráce – sestavení  
 Typy můžete najít v primární spolupracující sestavení, které nejsou viditelné pro jazyk VBA kvůli implementaci rozdíly. VBA poskytuje přehled modelu objektů aplikace Visio obsahující pouze objekty a členy, které můžete použít přímo. Primární spolupracující sestavení vystavit stejného objektu modelu, ale také obsahují další rozhraní, třídy a členy, kteří překládat objekty v modelu COM objektu do spravovaného kódu. Tyto další položky nejsou určena pro použití přímo v kódu.  
  
 Další informace najdete v tématu [přehled třídy a rozhraní v primární zprostředkovatel komunikace s objekty sestavení sady Office](http://go.microsoft.com/fwlink/?LinkId=189592) a [primární zprostředkovatel komunikace s objekty sestavení sady Office](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="see-also"></a>Viz také  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Práce s dokumenty aplikace Visio](../vsto/working-with-visio-documents.md)   
 [Práce s obrazci aplikace Visio](../vsto/working-with-visio-shapes.md)  
  
  