---
title: Přístup k vyrovnávací paměti textu s použitím rozhraní API pro starší verze | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text buffers
ms.assetid: cd6cf4ae-fff5-4e23-b293-7cbafdb8aed2
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f2cfbd84bc4f9298358a2a2d1ba87f76d6e5303c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54764098"
---
# <a name="accessing-the-text-buffer-by-using-the-legacy-api"></a>Přístup k vyrovnávací paměti textu s použitím rozhraní API pro starší verze
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Text zodpovídá za správu textových datových proudů a trvalost souborů. I když vyrovnávací paměti může číst nebo zapisovat dalších formátů, všechny běžné komunikaci s vyrovnávací paměť je prováděno pomocí kódování Unicode. Ve starší verzi rozhraní API můžete textovou vyrovnávací paměť použít buď jeden – nebo dvojrozměrné souřadnicový systém k identifikaci umístění znaku ve vyrovnávací paměti.  
  
## <a name="one--and-two-dimension-coordinate-systems"></a>Jeden a dvě dimenze koordinovat systémy  
 Jednorozměrný souřadnice polohy je založená na pozici znaku od prvního znaku ve vyrovnávací paměti, jako je například 147. Můžete použít <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> rozhraní pro přístup k jednorozměrné umístění ve vyrovnávací paměti. Dvojrozměrné souřadnice systém je založen na dvojice řádku a indexu. Například znak ve vyrovnávací paměti na 43 by být 5 na řádku 43 pět znaků napravo od prvního znaku v daném řádku. Přístup k dvojrozměrné umístění ve vyrovnávací paměti pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> rozhraní. Jak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> rozhraní implementují objekt vyrovnávací paměti textu (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>) a je přístupný od sebe navzájem pomocí `QueryInterface`. Následující diagram znázorňuje tyto a další klíče rozhraní na <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 ![Text Buffer Object](../extensibility/media/vstextbuffer.gif "vsTextBuffer")  
Objekt vyrovnávací paměť textu  
  
 Přestože buď souřadnicový systém funguje ve vyrovnávací paměti textu, je optimalizován pro použití dvojrozměrné souřadnice. Jednorozměrný souřadnicový systém můžete vytvořit nároky na výkon. Proto systém dvojrozměrné souřadnice kdykoli je to možné.  
  
 Trvalost souborů je text druhého odpovědnost přípravné vyrovnávací paměti. K tomuto účelu implementuje objekt vyrovnávací paměti textu <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> a funguje jako součást objektu data dokumentů pro položky projektu a další prostředí součásti účastnící se trvalosti. Další informace najdete v tématu [otevření a uložení položek projektu](../extensibility/internals/opening-and-saving-project-items.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Změna nastavení zobrazení pomocí zastaralého rozhraní API](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 Vysvětluje, jak změnit nastavení zobrazení pomocí starší verze rozhraní API.  
  
 [Použití textového správce k monitorování globálního nastavení](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 Vysvětluje, jak použít textový správce k monitorování globální nastavení...  
  
## <a name="see-also"></a>Viz také  
 [Práce v základní editoru](../extensibility/inside-the-core-editor.md)
