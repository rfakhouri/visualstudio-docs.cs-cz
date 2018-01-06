---
title: "Správa dokumentů na serveru s použitím třídy ServerDocument | Microsoft Docs"
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
- documents [Office development in Visual Studio], managing on server
- Office documents [Office development in Visual Studio, managing on server
- ServerDocument class, managing documents on server
ms.assetid: 1ac90e89-d07d-4874-9d24-6741d6679a21
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 96d69ccb51be632440474bb0aa1b32e6ebe7a68a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="managing-documents-on-a-server-by-using-the-serverdocument-class"></a>Správa dokumentů na serveru s použitím třídy ServerDocument
  Použitím třídy ServerDocument v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] spravovat několik aspektů přizpůsobení na úrovni dokumentu, i když nejsou nainstalované aplikace Microsoft Office Word a Microsoft Office Excel. Můžete provádět následující úlohy:  
  
-   Přístup a upravovat data v datové mezipaměti dokumentu nebo sešitu. Další informace najdete v tématu [práce s mezipaměti Data v dokumentu](#CachedData).  
  
-   Spravujte přizpůsobení sestavení, která je přidružena k dokumentu. Další informace najdete v tématu [Správa přizpůsobení dokumentu](#CustomizationInfo).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="understanding-the-serverdocument-class"></a>Vysvětlení třídy ServerDocument  
 Třídy ServerDocument je určen k použití na počítačích, které nemají nainstalovaný Office. Proto obvykle použijete této třídy v aplikacích, které nelze integrovat Office, jako jsou projekty konzoly nebo projekty Windows Forms, nikoli projektů Office. Použití <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy v sestavení Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll.  
  
 Třídy ServerDocument lze použít k provozu na úpravy na úrovni dokumentů, které byly vytvořeny pomocí [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)].  
  
 Další informace o sadu Visual Studio 2010 Tools pro systém Office Runtime, Office rozšíření pro rozhraní .NET Framework, najdete v části [Visual Studio Tools for Office Runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
> [!NOTE]  
>  Pokud máte starší verzi aplikace, která používá třídy ServerDocument ve Visual Studio Tools pro systém Office (verze 3.0 Runtime), sady Visual Studio Tools for Office system (verze 3.0 Runtime) musí být nainstalován v počítačích se systémem aplikace. Tyto aplikace nelze spustit sadu Visual Studio 2010 Tools for Office Runtime.  
  
##  <a name="CachedData"></a>Práce s Data uložená v mezipaměti v dokumentu  
 Třídy ServerDocument poskytuje členů, které můžete použít pro práci s mezipamětí dat ve vlastní dokumenty. Další informace o data uložená v mezipaměti najdete v tématu [ukládání dat do mezipaměti](../vsto/caching-data.md) a [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).  
  
 Následující tabulka uvádí členy, které můžete použít pro práci s data uložená v mezipaměti.  
  
|Úloha|Člen používat|  
|----------|-------------------|  
|Chcete-li zjistit, jestli má dokument datové mezipaměti.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.IsCacheEnabled%2A> Metoda.|  
|Pro přístup k data uložená v mezipaměti v dokumentu.<br /><br /> Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> Vlastnost.|  
  
##  <a name="CustomizationInfo"></a>Správa přizpůsobení dokumentu  
 Členy třídy ServerDocument můžete použít ke správě přizpůsobení sestavení, která je přidružena k dokumentu. Například můžete programově odebrat přizpůsobení z dokumentu tak, aby dokument je už součástí přizpůsobení.  
  
 Následující tabulka uvádí členy, které můžete použít ke správě přizpůsobení sestavení.  
  
|Úloha|Člen používat|  
|----------|-------------------|  
|K určení, zda dokument je součástí přizpůsobení na úrovni dokumentu.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.GetCustomizationVersion%2A> Metoda.|  
|Pro programové připojení přizpůsobení do dokumentu za běhu.<br /><br /> Další informace najdete v tématu [postupy: připojení spravovaných rozšíření kódu k dokumentům](../vsto/how-to-attach-managed-code-extensions-to-documents.md)|Jeden z <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> metody.|  
|Prostřednictvím kódu programu přizpůsobení odebrat z dokumentu za běhu.<br /><br /> Další informace najdete v tématu [postupy: odebrání spravovaných rozšíření kódu z dokumentů](../vsto/how-to-remove-managed-code-extensions-from-documents.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> Metoda.|  
|Získat adresu URL manifestu nasazení, který je přidružen dokumentu.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.DeploymentManifestUrl%2A> Vlastnost.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: připojení rozšíření spravovaného kódu k dokumentům](../vsto/how-to-attach-managed-code-extensions-to-documents.md)   
 [Postupy: odebrání rozšíření spravovaného kódu z dokumentů](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Visual Studio Tools for Office Runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Ukládaní dat do mezipaměti](../vsto/caching-data.md)  
  