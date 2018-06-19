---
title: Podpora pro uživatelských nastavení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Custom Settings Points
- user settings [Visual Studio SDK], registering persistence support
- persistence, registering settings
ms.assetid: ad9beac3-4f8d-4093-ad0e-6fb00444a709
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cf2ba79cc8bff57de1fd410f8a2780825d693181
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134085"
---
# <a name="support-for-user-settings"></a>Podpora pro uživatelských nastavení
VSPackage může definovat jeden nebo více kategorií nastavení, které jsou skupiny proměnné stavu, které zachovat, když uživatel vybere **nastavení importu a exportu** příkaz na **nástroje** nabídky. Pokud chcete povolit tento trvalost, použijete nastavení rozhraní API v [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].  
  
 Položky registru, který se označuje jako bod vlastní nastavení a identifikátor GUID definuje kategorie VSPackage nastavení. VSPackage může podporovat více nastavení kategorií, každý definované bod vlastní nastavení.  
  
-   Implementace nastavení, které jsou založeny na spolupráce – sestavení (pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> rozhraní) by měl vytvořit vlastní nastavení bod úpravy registru nebo pomocí skriptu registrátora (.rgs soubor). Další informace najdete v tématu [vytváření skripty registrátora](/cpp/atl/creating-registrar-scripts).  
  
-   Kód, který používá spravované balíček Framework (MPF) by měl vytvořit vlastní nastavení bodů připojením <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> k VSPackage pro každý bod vlastní nastavení.  
  
     Pokud jeden VSPackage podporuje několik bodů vlastní nastavení, každý bod vlastní nastavení je implementováno modulem samostatné třídy a každý je registrován ve jedinečný instanci <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> třídy. Nastavení, implementace třídy v důsledku toho může podporovat více než jednu kategorii nastavení.  
  
## <a name="custom-settings-point-registry-entry-details"></a>Podrobnosti o položku registru bodu vlastní nastavení  
 Vlastní nastavení body jsou vytvořené v položka registru v následujícím umístění: HKLM\Software\Microsoft\VisualStudio\\*\<verze >* \UserSettings\\`<CSPName>`, kde `<CSPName>` je název vlastního nastavení bodu podporuje VSPackage a  *\<verze >* je verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], například 8.0.  
  
> [!NOTE]
>  Kořenové cestě HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<verze >* lze přepsat pomocí náhradní root, kdy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) inicializovat. Další informace najdete v tématu [přepínače příkazového řádku](../../extensibility/command-line-switches-visual-studio-sdk.md).  
  
 Dole je zobrazená strukturu položky registru:  
  
 HKLM\Software\Microsoft\VisualStudio\\*\<verze >* \UserSettings\  
  
 `<CSPName`> = s: 12345 #.  
  
 Balíček = "{XXXXXX XXXX XXXX XXXX XXXXXXXXX}.  
  
 Kategorie = "{YYYYYY rrrr rrrr rrrr YYYYYYYYY}.  
  
 ResourcePackage = "{ZZZZZZ ZZZZ ZZZZ ZZZZ ZZZZZZZZZ}.  
  
 AlternateParent = CategoryName  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|(Výchozí)|REG_SZ|Název bodu vlastní nastavení|Název klíče `<CSPName`>, je název nelokalizované bodu vlastní nastavení.<br /><br /> Pro implementace sady MPF podle, je tím, že zkombinujete získat název klíče `categoryName` a `objectName` argumenty <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> konstruktor do `categoryName_objectName`.<br /><br /> Klíč nesmí být prázdné nebo může obsahovat ID odkazu lokalizovaný řetězec v satelitní knihovny DLL. Tato hodnota se získávají z `objectNameResourceID` argument <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> konstruktor.|  
|Balíček|REG_SZ|GUID|Identifikátor GUID VSPackage, který implementuje bodem vlastní nastavení.<br /><br /> Implementace založená na využívání sady MPF <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> třídy, použijte v konstruktoru `objectType` argument obsahující VSPackage <xref:System.Type> a reflexe získat tuto hodnotu.|  
|Kategorie|REG_SZ|GUID|Identifikátor GUID identifikace kategorie nastavení.<br /><br /> Pro implementace založené na sestavení vzájemné spolupráce, tato hodnota může být libovolně zvolený identifikátor GUID, který [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE předá do <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ExportSettings%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> metody. Všechny implementace tyto dvě metody by měl ověřit jejich argumenty identifikátor GUID.<br /><br /> Pro implementace sady MPF podle, je tento identifikátor GUID získané <xref:System.Type> implementace třídy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] mechanismus nastavení.|  
|ResourcePackage|REG_SZ|GUID|Volitelné.<br /><br /> Cesta k satelitní knihovny DLL obsahující lokalizované řetězce, pokud je neposkytuje implementující VSPackage.<br /><br /> Sady MPF používá reflexe získat správný zdroj VSPackage, proto <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> třída nenastaví tento argument.|  
|AlternateParent|REG_SZ|Název složky v části na stránce Možnosti nástroje obsahující tento bod vlastní nastavení.|Volitelné.<br /><br /> Tato hodnota musíte nastavit jenom v případě, že nastavení implementace podporuje **možnosti nástrojů** stránky, které používají tento mechanismus trvalosti v [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] místo mechanismus ve model automatizace pro uložení stavu.<br /><br /> V těchto případech je hodnota v klíči AlternateParent `topic` části `topic.sub-topic` řetězec se používá k identifikaci konkrétní **ToolsOptions** stránky. Například **ToolsOptions** stránky `"TextEditor.Basic"` by být hodnota parametru AlternateParent `"TextEditor"`.<br /><br /> Když <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> generuje bodem vlastní nastavení je stejný jako název kategorie.|