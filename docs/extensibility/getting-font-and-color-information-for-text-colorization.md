---
title: "Získávání písma a barev informace pro Text zabarvení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text, coloring
- font and color control [Visual Studio SDK], coloring
ms.assetid: d1f985bd-743e-40b7-9458-d9af53647c91
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e3b31ad2ec080070dec3c68b304f400d204d47a0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="getting-font-and-color-information-for-text-colorization"></a>Získávání písma a barev informace pro zabarvení textu
Proces, který vykreslí nebo obarvené text se zobrazí prvky uživatelského rozhraní (UI) závisí na typu projektu, technologie a vývojáře předvolby. **Písma a barev** stránka vlastností ukládá nastavení.  
  
 Třeba většinu implementací, které zobrazit obarvené text `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults` a přidružené rozhraní pro nastavení zobrazení prezentací, načítání a ukládání textu.  
  
> [!NOTE]
>  Při přizpůsobování editoru jádra (který podporuje **Text EditorCategory**), důrazně doporučujeme pomocí technologie barevné zvýrazňování ve službě jazyk. Další informace najdete v tématu [písma a barev přehled](../extensibility/font-and-color-overview.md).  
  
## <a name="getting-default-font-and-color-information"></a>Získávání výchozí písma a barev informace  
 Všechny **písma a barev** nastavení časového období zobrazení textu musí být zadán v **zobrazení položky** jednoho **kategorie**. Další informace najdete v tématu [písma a barvy, prostředí, dialogové okno Možnosti](../ide/reference/fonts-and-colors-environment-options-dialog-box.md).  
  
 Kolorovat, musíte získat VSPackage aktuální **písma a barev** nastavení. VSPackage to můžete udělat následujícími způsoby v závislosti na jeho potřeb:  
  
-   Umožňuje načíst uložené nebo aktuální stav mechanismus trvalosti písma a barvy. Další informace najdete v tématu [přístup k uložené písma a barev nastavení](../extensibility/accessing-stored-font-and-color-settings.md).  
  
-   Použití <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> rozhraní služby poskytuje písma a barev data získat instanci <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>, pokud VSPackage není také zprostředkovatele písma a barvy.  
  
-   Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> rozhraní.  
  
 Chcete, aby získala při dotazování na výsledky jsou aktuální, může být užitečné používat <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> rozhraní k určení, pokud je třeba aktualizace před voláním metody načtení <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> rozhraní.  
  
 Po můžete získat informace o písma a barev, analyzovat text, který má být zobrazen pro identifikaci elementy, které vyžadují zabarvení a následně se zobrazí text v okně pomocí příslušná písma a barvy.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>   
 [Použití písem a textu](/dotnet/framework/winforms/advanced/using-fonts-and-text)   
 [Práce s barvou](/cpp/windows/working-with-color-image-editor-for-icons)   
 [GDI (rozhraní grafiky zařízení)](http://msdn.microsoft.com/en-us/7e1d4540-bb2e-4257-8eee-eee376acba83)