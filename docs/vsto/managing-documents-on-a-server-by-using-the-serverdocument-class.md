---
title: Správa dokumentů na serveru s použitím třídy ServerDocument
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], managing on server
- Office documents [Office development in Visual Studio, managing on server
- ServerDocument class, managing documents on server
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 97eed0e4cec143e51195347bfb90d430d8e1eadb
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572995"
---
# <a name="manage-documents-on-a-server-by-using-the-serverdocument-class"></a>Správa dokumentů na serveru s použitím třídy ServerDocument
  Můžete použít `ServerDocument` třídy v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] spravovat několik aspektů přizpůsobení na úrovni dokumentu, i když nejsou nainstalované aplikace Microsoft Office Word a Microsoft Office Excel. Můžete provádět následující úlohy:  
  
-   Přístup a upravovat data v datové mezipaměti dokumentu nebo sešitu. Další informace najdete v tématu [práce s data uložená v mezipaměti v dokumentu](#CachedData).  
  
-   Spravujte přizpůsobení sestavení, která je přidružena k dokumentu. Další informace najdete v tématu [spravovat přizpůsobení dokumentu](#CustomizationInfo).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="understand-the-serverdocument-class"></a>Pochopení ServerDocument – třída  
 `ServerDocument` Třída je určen k použití na počítačích, které nemají nainstalovaný Office. Proto obvykle použijete této třídy v aplikacích, které nelze integrovat Office, jako jsou projekty konzoly nebo projekty Windows Forms, nikoli projektů Office. Použití <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy v *Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll* sestavení.  
  
 `ServerDocument` Třídu lze použít k provozu na úpravy na úrovni dokumentů, které byly vytvořeny pomocí [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)].  
  
 Další informace o sadu Visual Studio 2010 Tools pro systém Office Runtime, Office rozšíření pro rozhraní .NET Framework, najdete v části [Visual Studio Tools for Office runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
> [!NOTE]  
>  Pokud máte starší verzi aplikace, která používá `ServerDocument` třídy v `Visual Studio Tools for Office` system (verze 3.0 Runtime), `Visual Studio Tools for Office` system (verze 3.0 runtime) musí být nainstalované na počítačích, pro spuštění aplikace. `Visual Studio 2010 Tools for Office runtime` Nelze spustit tyto aplikace.  
  
##  <a name="CachedData"></a> Práce s data uložená v mezipaměti v dokumentu  
 `ServerDocument` Třída poskytuje členy můžete použít pro práci s mezipamětí dat ve vlastní dokumenty. Další informace o data uložená v mezipaměti najdete v tématu [ukládat data do mezipaměti](../vsto/caching-data.md) a [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).  
  
 Následující tabulka uvádí členy, které můžete použít pro práci s data uložená v mezipaměti.  
  
|Úloha|Člen používat|  
|----------|-------------------|  
|Chcete-li zjistit, jestli má dokument datové mezipaměti.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.IsCacheEnabled%2A> Metoda.|  
|Pro přístup k data uložená v mezipaměti v dokumentu.<br /><br /> Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> Vlastnost.|  
  
##  <a name="CustomizationInfo"></a> Spravovat přizpůsobení dokumentu  
 Můžete použít členy `ServerDocument` třídy ke správě přizpůsobení sestavení, která je přidružena k dokumentu. Například můžete programově odebrat přizpůsobení z dokumentu tak, aby dokument je už součástí přizpůsobení.  
  
 Následující tabulka uvádí členy, které můžete použít ke správě přizpůsobení sestavení.  
  
|Úloha|Člen používat|  
|----------|-------------------|  
|K určení, zda dokument je součástí přizpůsobení na úrovni dokumentu.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.GetCustomizationVersion%2A> Metoda.|  
|Pro přizpůsobení programové připojení k dokumentu za běhu.<br /><br /> Další informace najdete v tématu [postupy: připojení spravovaných rozšíření kódu k dokumentům](../vsto/how-to-attach-managed-code-extensions-to-documents.md)|Jeden z <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> metody.|  
|Prostřednictvím kódu programu přizpůsobení odebrat z dokumentu za běhu.<br /><br /> Další informace najdete v tématu [postupy: odebrání spravovaný kód rozšíření z dokumentů](../vsto/how-to-remove-managed-code-extensions-from-documents.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> Metoda.|  
|Získat adresu URL manifestu nasazení, který je přidružen dokumentu.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.DeploymentManifestUrl%2A> Vlastnost.|  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: připojení spravovaných rozšíření kódu k dokumentům](../vsto/how-to-attach-managed-code-extensions-to-documents.md)   
 [Postupy: odebrání spravovaných rozšíření kódu z dokumentů](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Visual Studio Tools for Office runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Data do mezipaměti](../vsto/caching-data.md)  
  