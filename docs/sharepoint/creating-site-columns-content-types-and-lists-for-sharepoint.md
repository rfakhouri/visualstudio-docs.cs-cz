---
title: "Vytváření sloupců webu, typů obsahu a seznamů pro službu SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.ListDesigner.ContentTypeSetting
- VS.SharePointTools.ContentTypeDesigner.CommonPropertiesPage
- VS.SharePointTools.ListDesigner.CreatingLists
- VS.SharePointTools.ListDesigner.ListPage
- VS.SharePointTools.ListDesigner.ViewPage
- VS.SharePointTools.ListDesigner.CommonPropertiesPage
- VS.SharePointTools.ContentTypeDesigner.ColumnsPage
dev_langs:
- VB
- CSharp
ms.assetid: 9ceed263-3aec-41dc-8708-63cb37a08fa8
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4b7a2d1be80e7c8bde780499894bccd82c572a16
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-site-columns-content-types-and-lists-for-sharepoint"></a>Vytváření sloupců webu, typů obsahu a seznamů pro službu SharePoint
  Visual Studio poskytuje šablony položek projektu pro mnoho různých základní položek služby SharePoint, včetně *uvádí* a *typů obsahu*, která můžete začlenit sloupců webu (nebo  *pole*). Nové Designer pro seznamy a typy obsahu zkontrolujte vytváření těchto položek jednodušší než kdy dřív.  
  
## <a name="site-columns"></a>Sloupce webu  
 Sloupce webu jsou jedním z nejzákladnější prvky, které přidáte do projektu služby SharePoint. Sloupec lokality představuje typ dat, například telefonní číslo, komentář nebo název města kontaktu, seznamu kontaktů.  
  
 Šablony položky projektu sloupce nové lokality usnadňuje vytváření sloupců webu než ve starší verzi sady Visual Studio. Po vytvoření nového sloupce webu, můžete upravit soubor XML v souboru Elements.xml sloupec lokality zahrnují informace, které chcete, například jeho zobrazovaný název, typ dat a skupiny, ve kterém má sloupec lokality zobrazí ve službě SharePoint. Další informace o sloupců webu najdete v tématu [Úvod do sloupce](http://go.microsoft.com/fwlink/?LinkId=224996).  
  
## <a name="content-types-and-lists"></a>Seznamy a typy obsahu  
 Seznamy a typy obsahu patří mezi nejčastěji používaných prvků ve službě SharePoint.  
  
 Typ obsahu definuje metadata, pracovní postup a chování pro kategorii položek v knihovně služby SharePoint seznamu nebo dokumentu. Můžete například vytvořit typ obsahu informace v seznamu kontaktů nebo seznamu úloh. Typ obsahu kontaktu mohou zahrnovat sloupců, jako je jméno, e-mailu, telefonní číslo a adresu. Typ obsahu, který můžete definovat na úrovni webu nezávisí na žádné seznam nebo knihovna dokumentů v lokalitě. Jiné seznamy nebo knihovny dokumentů na webu služby SharePoint můžete použít stejný typ obsahu. Můžete taky několik typů obsahu na stejný seznam nebo knihovnu dokumentů.  
  
 Seznam je kolekce informací ve službě SharePoint, které můžete sdílet s ostatními. Seznamy obsahovat řádků sloupců, které obsahují data. Některé příklady seznamy: seznam úkolů, seznamu kontaktů a seznam oznámení.  
  
 Nový typ obsahu a seznamu Designer v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zkontrolujte vytváření seznamy a typy obsahu webu mnohem snazší a intuitivnější než ve starší verzi sady Visual Studio. Uživatelské rozhraní umožňuje vizuálně známé způsobem vytvořit seznamy a typy obsahu a umožňuje řazení a seskupování dat v seznamech a použít záhlaví skupiny. Další informace o typech obsahu najdete v tématu [typy obsahu](http://go.microsoft.com/fwlink/?LinkId=224997). Další informace o seznamech najdete v tématu [seznamu Forms](http://go.microsoft.com/fwlink/?LinkId=224998) a [zobrazení seznamu](http://go.microsoft.com/fwlink/?LinkId=224999).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Návod: Vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)|Demonstruje postup vytvoření sloupce webu, které se používají v vlastní typ obsahu. Typ obsahu se pak používá vlastní seznamu.|  
  
## <a name="see-also"></a>Viz také  
 [Začít s vývojem na verzi SharePoint 2010](http://go.microsoft.com/fwlink/?LinkId=225000)  
  
  