---
title: 'Postupy: Použití značek Text | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - using text markers
ms.assetid: 76eed51c-eecb-4579-823e-13df2f0526b9
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 25c3c4f3a3d9a253b9ec671892d0d44ccf9ca3ab
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63430964"
---
# <a name="how-to-use-text-markers"></a>Postupy: Použití značek Text
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Textu značky lze použít k úpravě <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> objektu.  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-apply-text-markers"></a>Chcete-li použít text značky  
  
1. Získání instance <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> třídy.  
  
    > [!NOTE]
    > Základní editor automaticky aplikuje standardní text značky na všechny dokumenty, které je úpravy a neměl by být nutné explicitní použití standardního textu značky.  
  
2. Získat Identifikátor značky typu značky jsou zajímá voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> metodu s `GUID` text značky chcete pracovat.  
  
    > [!NOTE]
    > Nepoužívejte `GUID` sady VSPackage nebo služby, která obsahuje text značky.  
  
3. Použití ID typu značky získán voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> metodu jako parametr pro volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> metoda nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> způsob, jak použít značku textu pro danou oblast textu.  
  
#### <a name="to-add-features-to-text-markers"></a>Přidávání funkcí do textu značky  
  
1. Může být vhodné pro přidání dalších funkcí do textu značky, jako jsou popisy tlačítek, speciální místní nabídky nebo obslužná rutina pro zvláštní okolnosti. Postup:  
  
2. Vytvoření implementace objektu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní.  
  
3. V případě potřeby je další funkce, implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced> rozhraní na stejný objekt, který implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní.  
  
4. Předání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní, které vytvoříte, volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> metoda nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> metoda používá k aplikování text značky pro danou oblast textu.  
  
5. Při přidávání kontextové nabídky podpory do oblasti značky text je potřeba vytvořit v nabídce.  
  
     Další informace o tom, jak vytvořit kontextové nabídky, naleznete v tématu [kontextové nabídky](../extensibility/context-menus.md).  
  
6. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Prostředí volání metody zadané rozhraní, jako <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetTipText%2A> metodu, nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> metoda podle potřeby.  
  
## <a name="see-also"></a>Viz také  
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Postupy: Přidání standardní Text značky](../extensibility/how-to-add-standard-text-markers.md)   
 [Postupy: Vytvoření vlastního textu značky](../extensibility/how-to-create-custom-text-markers.md)   
 [Postupy: Implementace chybových značek](../extensibility/how-to-implement-error-markers.md)
