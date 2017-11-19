---
title: "Postupy: zobrazení dokumentů dat připojit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - attach views to document data
ms.assetid: f92c0838-45be-42b8-9c55-713e9bb8df07
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 146303eebbd824342b000fb14b8dbf953c3f0523
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-attach-views-to-document-data"></a>Postupy: zobrazení dokumentů datové připojení
Pokud máte nové zobrazení dokumentů, bude pravděpodobně možné připojit k existující data objektu dokumentu.  
  
### <a name="to-determine-if-you-can-attach-a-view-to-an-existing-document-data-object"></a>Chcete-li zjistit, pokud zobrazení můžete připojit k existující data objektu dokumentu  
  
1.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>.  
  
2.  V implementaci `IVsEditorFactory::CreateEditorInstance`, volání `QueryInterface` na existující data objektu dokumentu při volání rozhraní IDE vaší `CreateEditorInstance` implementace.  
  
     Volání metody `QueryInterface` můžete prozkoumat datový objekt existující dokument, který je uveden v `punkDocDataExisting` parametr.  
  
     Přesný rozhraní, které musí dotazování, je však závisí na editor, který je otevření dokumentu, jak je uvedeno v kroku 4.  
  
3.  Pokud příslušná rozhraní na existující data objektu dokumentu nenajdete, bude vrácen chybový kód k editoru označující, že datový objekt dokumentu je nekompatibilní s vaší editor.  
  
     Implementace rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, okno se zprávou vás upozorní, že dokument je otevřený v jiném editoru a požádá, pokud budete chtít ji uzavřít.  
  
4.  Pokud zavřete tento dokument, Visual Studio volá vaše objekt factory editoru pro ještě jednou. Na toto volání `DocDataExisting` rovná parametru na hodnotu NULL. Vaše implementace objektu factory editoru pak můžete otevřít dokument datový objekt ve svém vlastním editoru.  
  
    > [!NOTE]
    >  Pokud chcete zjistit, zda můžete pracovat s existujícím objektem dat dokumentu, můžete použít také privátní znalosti o implementaci rozhraní podle přetypování ukazatel na skutečnou [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] třídu vaší privátní implementace. Například všechny standardní editory implementovat `IVsPersistFileFormat`, který dědí z <xref:Microsoft.VisualStudio.OLE.Interop.IPersist>. Proto můžete volat `QueryInterface` pro <xref:Microsoft.VisualStudio.OLE.Interop.IPersist.GetClassID%2A>, a pokud ID třídy na existující data objektu dokumentu odpovídá vaší implementace ID třídy a pak můžete pracovat s datový objekt dokumentu.  
  
## <a name="robust-programming"></a>Robustní programování  
 Když Visual Studio volá vaši implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda, pak předá zpět ukazatel existující objekt dat dokumentu v `punkDocDataExisting` parametr, pokud existuje. Zkontrolujte dokumentu datový objekt vrácený v `punkDocDataExisting` lze zjistit datový objekt dokumentu je vhodné pro vaše editor, jak je uvedeno v poznámce v kroku 4 v postupu v tomto tématu. Pokud je vhodné, pak vaše objekt factory editoru by měl poskytovat druhý zobrazení pro data, jak je uvedeno v [podpora více zobrazení dokumentu](../extensibility/supporting-multiple-document-views.md). Pokud ne, pak se má zobrazit příslušná chybová zpráva.  
  
## <a name="see-also"></a>Viz také  
 [Podpora více zobrazení dokumentu](../extensibility/supporting-multiple-document-views.md)   
 [Data dokumentu a zobrazení dokumentu vlastní editorů](../extensibility/document-data-and-document-view-in-custom-editors.md)