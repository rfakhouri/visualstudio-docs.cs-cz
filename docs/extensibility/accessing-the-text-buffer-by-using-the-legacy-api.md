---
title: "Přístup k textová vyrovnávací paměť s použitím rozhraní API starší | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - text buffers
ms.assetid: cd6cf4ae-fff5-4e23-b293-7cbafdb8aed2
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 77002e095690da85e73f1a79d405cb5174b96851
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-the-text-buffer-by-using-the-legacy-api"></a>Přístup k textová vyrovnávací paměť s použitím rozhraní API starší verze
Text je zodpovědný za správu textové datové proudy a soubor trvalost. I když vyrovnávací paměti můžou číst nebo zapisovat dalších formátů, všechny běžné komunikace s vyrovnávací paměti se provádí pomocí kódování Unicode. Ve starší verzi rozhraní API textovou vyrovnávací paměť můžete použít jeden – nebo dvourozměrná souřadnicový systém můžete určit umístění znaku ve vyrovnávací paměti.  
  
## <a name="one--and-two-dimension-coordinate-systems"></a>Jedna a dvě dimenze koordinaci systémy  
 Jednorozměrná souřadnice polohy je založena na znak na pozici od prvního znaku ve vyrovnávací paměti, jako je například 147. Můžete použít <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> rozhraní přistupovat k jednorozměrné umístění ve vyrovnávací paměti. Dvourozměrná souřadnicový systém vychází z dvojice řádku a indexu. Například znak ve vyrovnávací paměti na 43, by být 5 na řádku 43, pět znaků napravo od první znak v daného řádku. Přístup dvourozměrná umístění do vyrovnávací paměti pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> rozhraní. Jak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> rozhraní jsou implementované objekt textové vyrovnávací paměti (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>) a je přístupný pomocí od sebe navzájem `QueryInterface`. Následující diagram znázorňuje těchto a dalších klíče rozhraní na <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 ![Objekt vyrovnávací paměti textu](../extensibility/media/vstextbuffer.gif "vsTextBuffer")  
Objekt textové vyrovnávací paměti  
  
 I když buď souřadnicový systém funguje v textová vyrovnávací paměť, je optimalizován pro používání dvourozměrná souřadnic. Jednorozměrná souřadnicový systém můžete vytvořit nároky na výkon. Proto používejte dvourozměrná souřadnicový systém kdykoli je to možné.  
  
 Text druhý odpovědnost vyrovnávací paměti je soubor trvalost. K tomuto účelu implementuje objekt textové vyrovnávací paměti <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> a funguje jako součást dokumentu data objektu pro položky projektu a dalších prostředí součásti účastnící se trvalost. Další informace najdete v tématu [otevírání a ukládání položky projektu](../extensibility/internals/opening-and-saving-project-items.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Změna nastavení zobrazení pomocí starší verze rozhraní API](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 Vysvětluje, jak chcete-li změnit nastavení zobrazení pomocí starší verze rozhraní API.  
  
 [Pomocí Správce Text k monitorování globální nastavení](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 Vysvětluje, jak používat text manager ke sledování globální nastavení...  
  
## <a name="see-also"></a>Viz také  
 [V editoru jádra](../extensibility/inside-the-core-editor.md)