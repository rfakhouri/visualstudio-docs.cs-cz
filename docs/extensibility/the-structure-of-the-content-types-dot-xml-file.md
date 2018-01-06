---
title: Struktura souboru XML [Content_types] | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- content_types
- content types
- opc
- vsix
ms.assetid: 9c399598-b9fa-4da7-84b5-defbf82e9335
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 08f1bb76f27f7ae0923eed43339f656c90f4856f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="the-structure-of-the-contenttypesxml-file"></a>Struktura souboru XML [Content_types]
Obsahuje informace o typech obsahu v balíčku VSIX. Visual Studio použije k instalaci balíčku [Content_Types] soubor .xml, ale nenainstaluje samotném souboru.  
  
> [!NOTE]
>  I když toto téma se vztahuje pouze na soubory [typ_obsahu] .xml, které se používají v balíčcích VSIX, typ souboru .xml [Content_Types] je součástí *otevřete balení konvence (OPC)* standardní. Další informace najdete v tématu [OPC: A nová standardní pro balení vaše Data](http://go.microsoft.com/fwlink/?LinkID=148207) na webu MSDN.  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují kořenového elementu a jeho atributy a podřízené elementy.  
  
### <a name="root-element"></a>Kořenový Element  
  
|Prvek|Popis|  
|-------------|-----------------|  
|`Types`|Obsahuje podřízené prvky, které zobrazí výčet typů souborů v balíčku VSIX.|  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Xmlns`|(Povinné). Umístění schématu pro tento soubor .xml [Content_Types].|  
  
### <a name="attribute-name-attribute"></a>{Atribut name} Atribut  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|http://schemas.openformats.org/Package/2006/Content-Types|Umístění schéma typy obsahu.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 `Types` Element může obsahovat libovolný počet `Default` elementy.  
  
|Prvek|Popis|  
|-------------|-----------------|  
|`Default`|Popisuje typ obsahu v balíčku VSIX. Všechny typy souborů v balíčku musí mít svůj vlastní `Default` elementu.|  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Extension`|Přípona názvu souboru souboru v balíčku VSIX.|  
|`ContentType`|Popisuje typ obsahu, který je přidružen k příponě názvu souboru.|  
  
### <a name="attribute-name-attribute"></a>{Atribut name} Atribut  
 Visual Studio rozpozná následující `ContentType` hodnoty pro přidruženého `Extension` typy.  
  
|Rozšíření|Typ obsahu|  
|---------------|-----------------|  
|TXT|text/plain|  
|pkgdef|text/plain|  
|XML|text/xml|  
|vsixmanifest|text/xml|  
|htm nebo html|text/html|  
|RTF|aplikace nebo rtf|  
|PDF|aplikace nebo souboru pdf|  
|GIF|bitové kopie nebo gif|  
|JPG nebo jpeg|bitové kopie nebo jpg|  
|TIFF|bitové kopie nebo tiff|  
|vsix|aplikace nebo zip|  
|ZIP|aplikace nebo zip|  
|knihovny DLL|application/octet-stream|  
|všechny ostatní typy souborů|application/octet-stream|  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující soubor .xml [Content_Types] popisuje typického balíčku VSIX.  
  
### <a name="code"></a>Kód  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types">  
    <Default Extension="vsixmanifest" ContentType="text/xml" />   
    <Default Extension="dll" ContentType="application/octet-stream" />   
    <Default Extension="png" ContentType="application/octet-stream" />   
    <Default Extension="txt" ContentType="text/plain" />   
    <Default Extension="pkgdef" ContentType="text/plain" />   
</Types>  
```  
  
## <a name="see-also"></a>Viz také  
 [Anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md)   
 [Referenční dokumentace schématu 1.0 rozšíření VSIX](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [OPC: Se novým standardem pro balení vaše Data](http://go.microsoft.com/fwlink/?LinkID=148207)