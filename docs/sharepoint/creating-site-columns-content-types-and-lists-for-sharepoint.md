---
title: Vytváření sloupců webu, typů obsahu a seznamů pro službu SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 805500b9f12e227e95add02ca0180b658b85d1cf
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53931944"
---
# <a name="create-site-columns-content-types-and-lists-for-sharepoint"></a>Vytváření sloupců webu, typů obsahu a seznamů pro službu SharePoint
  Visual Studio obsahuje šablony položek projektu pro mnoho různých základní položek služby SharePoint, včetně *uvádí* a *typů obsahu*, které můžete začlenit sloupců webu (nebo  *pole*). Návrháři nových typů obsahu a seznamů Ujistěte se, vytváří tyto položky se nyní ještě snazší.  
  
## <a name="site-columns"></a>Sloupce webu
 Sloupce webu jsou základní prvky, které přidáte do projektu služby SharePoint. Sloupec webu představuje typ dat, jako je například telefonní číslo, komentáře nebo název města kontaktu v seznamu kontaktů.  
  
 Šablony položky projektu sloupce nové lokality usnadňuje vytváření sloupců webu než v předchozích verzích sady Visual Studio. Po vytvoření nového sloupce webu, můžete upravit kód XML v sloupce webu *Elements.xml* souboru pro zahrnutí informací, které chcete, jako je například své zobrazované jméno, jeho datový typ a skupiny, ve kterém chcete sloupec webu se zobrazí v SharePoint. Další informace o sloupců webu, naleznete v tématu [Úvod do sloupce](http://go.microsoft.com/fwlink/?LinkId=224996).  
  
## <a name="content-types-and-lists"></a>Typy obsahu a seznamů
 Typy obsahu a seznamů patří mezi nejčastěji používaných prvků v Sharepointu.  
  
 Typ obsahu definuje metadat, pracovní postup a chování pro kategorie položek v knihovně dokumentů nebo seznamu služby SharePoint. Můžete například vytvořit typ obsahu informace v seznamu kontaktů nebo seznamu úloh. Typ kontaktu obsahu může obsahovat sloupců, jako je jméno, e-mailu, telefonní číslo a adresu. Typ obsahu, který můžete definovat na úrovni webu nezávisí žádné seznam nebo knihovna dokumentů na webu. Různé seznamy nebo knihovny dokumentů na webu služby SharePoint můžete použít stejný typ obsahu. Můžete také použít několik typů obsahu na stejný seznam nebo knihovna dokumentů.  
  
 Seznam je kolekce informací ve službě SharePoint, které můžete sdílet s ostatními. Seznamy se skládají z řádků sloupců, které obsahují data. Některé příklady seznamy: seznam úkolů, seznam kontaktů a seznam oznámení.  
  
 Nový typ obsahu a seznamu návrhářů v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zkontrolujte vytváření typů obsahu webu a seznamů mnohem jednodušší a intuitivnější než v předchozích verzích sady Visual Studio. Uživatelské rozhraní umožňuje vizuálně sestavit typy obsahu a seznamů v podobě známé a umožňuje řazení a seskupení dat v seznamech a používat skupiny záhlaví. Další informace o typy obsahu, najdete v části [typy obsahu](http://go.microsoft.com/fwlink/?LinkId=224997). Další informace o seznamech najdete v tématu [formuláře seznamu](http://go.microsoft.com/fwlink/?LinkId=224998) a [seznamy](http://go.microsoft.com/fwlink/?LinkId=224999).  
  
## <a name="related-topics"></a>Související témata
  
|Název|Popis|  
|-----------|-----------------|  
|[Návod: Vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)|Popisuje způsob vytvoření sloupce webu, které se používají ve vlastní typ obsahu. Typ obsahu se pak použije v vlastního seznamu.|  
  
## <a name="see-also"></a>Viz také:
 [Začněte s vývojem na verzi SharePoint 2010](http://go.microsoft.com/fwlink/?LinkId=225000)  
