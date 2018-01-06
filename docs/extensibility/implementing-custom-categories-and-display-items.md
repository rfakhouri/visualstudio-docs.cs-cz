---
title: "Implementace vlastních kategorií a zobrazit položky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- font and color control [Visual Studio SDK], categories
- custom categories
ms.assetid: 99311a93-d642-4344-bbf9-ff6e7fa5bf7f
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2dedd54aa1db26e38b6f212c616bd38c09018961
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-custom-categories-and-display-items"></a>Implementace vlastních kategorií a zobrazit položky
VSPackage může poskytnout kontrolu nad písma a barvy jeho text, který [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) prostřednictvím vlastních kategorií a zobrazení položky.  
  
 Vlastní kategorie a zobrazit položky **písma a barev** stránku vlastností. Otevřete **písma a barev** vlastnost na stránce **nástroje** nabídky, klikněte na tlačítko **možnosti**. Rozbalte položku **prostředí** a pak klikněte na **písma a barev**.  
  
 Pokud používáte tento mechanismus, musí implementovat VSPackages <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> rozhraní a jeho přidružené rozhraní.  
  
 V zásadě, tento mechanismus slouží k úpravě všech existujících **zobrazení položek** a **kategorie** které je obsahují. Ale by neměl být používají k úpravě **Text EditorCategory** nebo jeho **zobrazení položek**. Další informace najdete v tématu [písma a barev přehled](../extensibility/font-and-color-overview.md).  
  
 K implementaci vlastních **kategorie** nebo **zobrazení položek**, VSPackage musí:  
  
-   Vytvořte nebo Identifikujte kategorií v registru.  
  
     Implementace rozhraní IDE **písma a barev** stránka vlastností používá tuto informaci k správně dotaz pro službu podpora dané kategorii.  
  
-   Vytvořte nebo Identifikujte skupin (volitelné) v registru.  
  
     Může být užitečné pro definování skupiny, která představuje sjednocení dvou nebo více kategorií. Pokud je definována skupinu, rozhraní IDE automaticky sloučí podkategorie a distribuuje zobrazit položky v rámci skupiny.  
  
-   Implementovat podpora rozhraní IDE.  
  
-   Zpracování změn písma a barvy.  
  
 Informace najdete v tématu [přístup k uložené písma a barev nastavení](../extensibility/accessing-stored-font-and-color-settings.md).  
  
## <a name="to-create-or-identify-categories"></a>K vytvoření nebo určení kategorií  
  
-   Vytvořit zvláštní druh položky registru kategorie [HKLM\SOFTWARE\Microsoft \Visual Studio\\*\<verze sady Visual Studio >*\FontAndColors\\`<Category>`]  
  
     *\<Kategorie >* je Nelokalizováno název kategorie.  
  
-   Naplnění registr s využitím dvou hodnot:  
  
    |Název|Typ|Data|Popis|  
    |----------|----------|----------|-----------------|  
    |Kategorie|REG_SZ|GUID|Identifikátor GUID vytvořit k identifikaci kategorii.|  
    |Balíček|REG_SZ|GUID|Identifikátor GUID VSPackage služby, která podporuje kategorii.|  
  
 Službu uvedený v registru musí poskytovat implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> pro odpovídající kategorii.  
  
## <a name="to-create-or-identify-groups"></a>K vytvoření nebo určení skupiny  
  
-   Vytvořit zvláštní druh položky registru kategorie [HKLM\SOFTWARE\Microsoft \Visual Studio\\*\<verze sady Visual Studio >*\FontAndColors\\  *\<skupiny >*]  
  
     *\<skupiny >* je Nelokalizováno název skupiny.  
  
-   Naplnění registr s využitím dvou hodnot:  
  
    |Název|Typ|Data|Popis|  
    |----------|----------|----------|-----------------|  
    |Kategorie|REG_SZ|GUID|Identifikátor GUID, Identifikujte skupinu vytvořit.|  
    |Balíček|REG_SZ|GUID|Identifikátor GUID služby, která podporuje kategorii.|  
  
 Službu uvedený v registru musí poskytovat implementace `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` pro odpovídající skupinu.  
  
## <a name="to-implement-ide-support"></a>K implementaci podpora rozhraní IDE  
  
-   Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider.GetObject%2A>, která vrací buď <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> rozhraní nebo `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` rozhraní IDE pro každou **kategorie** nebo skupinu identifikátorem GUID.  
  
-   Pro každý **kategorie** podporuje, VSPackage implementuje samostatnou instanci <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> rozhraní.  
  
-   Metody implementované pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> musíte zadat IDE se:  
  
    -   Seznamy **zobrazení položek** v **kategorie.**  
  
    -   Lokalizovatelný názvy **zobrazení položek**.  
  
    -   Zobrazení informací pro každého člena **kategorie**.  
  
    > [!NOTE]
    >  Každý **kategorie** musí obsahovat alespoň jeden **zobrazení položky**.  
  
-   Rozhraní IDE používá `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` rozhraní k definování spojení několika kategorií.  
  
     Jeho implementace poskytuje IDE se:  
  
    -   Seznam **kategorie** které tvoří dané skupiny.  
  
    -   Přístup k instancím typu <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> podpora každý **kategorie** ve skupině.  
  
    -   Názvy lokalizovatelný skupin.  
  
-   Probíhá aktualizace integrovaného vývojového prostředí:  
  
     Prostředí IDE uloží informace o **písma a barev** nastavení. Proto po všech změnách rozhraní IDE **písma a barev** konfigurace, se doporučuje, abyste měli jistotu, že je aktuální mezipaměti.  
  
 Aktualizace mezipaměti se provádí prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> rozhraní a lze provádět globálně nebo jenom na vybrané položky.  
  
## <a name="to-handle-font-and-color-changes"></a>Popisovač písma a barev změny  
 Pro podporu správně zabarvení text, který zobrazí VSPackage, službu zabarvení podpora VSPackage reagovat na uživatel spustil změny prostřednictvím **písma a barev** stránku vlastností. VSPackage dosahuje tím, že:  
  
-   Zpracování událostí generovaných IDE implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> rozhraní.  
  
     Prostředí IDE volá metodu odpovídající následující úpravy uživatele **písma a barev** stránky. Například volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents.OnFontChanged%2A> metoda, pokud je vybrána nového písma.  
  
     -nebo-  
  
-   Dotazování IDE pro změny.  
  
     To lze provést prostřednictvím systému implementovaná <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> rozhraní. I když především pro podporu trvalost, <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> metoda lze získat informace o písma a barev **zobrazení položek**. Další informace najdete v tématu [přístup k uložené písma a barev nastavení](../extensibility/accessing-stored-font-and-color-settings.md).  
  
    > [!NOTE]
    >  Chcete, aby získala při dotazování na výsledky jsou správné, může být užitečné používat <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> rozhraní k určení, pokud se před voláním metody načtení potřebuje vyprázdnění mezipaměti a aktualizace <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> rozhraní.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>   
 [Získávání písma a barev informace pro zabarvení textu](../extensibility/getting-font-and-color-information-for-text-colorization.md)   
 [Přístup k uložené písma a barev](../extensibility/accessing-stored-font-and-color-settings.md)   
 [Postupy: přístup k vestavěná písma a barevné schéma](../extensibility/how-to-access-the-built-in-fonts-and-color-scheme.md)   
 [Písma a barev – přehled](../extensibility/font-and-color-overview.md)