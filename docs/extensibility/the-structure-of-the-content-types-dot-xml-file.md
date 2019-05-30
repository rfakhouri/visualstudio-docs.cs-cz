---
title: Struktura souboru [Content_types] .xml | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- content_types
- content types
- opc
- vsix
ms.assetid: 9c399598-b9fa-4da7-84b5-defbf82e9335
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9ef77c610bd310347c7ba60048bda342e997da33
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66316419"
---
# <a name="the-structure-of-the-contenttypesxml-file"></a>Struktura souboru [Content_types].xml
Obsahuje informace o druzích obsah v balíčku souboru VSIX. Visual Studio používá k instalaci balíčku souboru [Content_Types] .xml, ale nenainstaluje samotný soubor.

> [!NOTE]
> I když toto téma se týká pouze soubory XML [Content_Type], které se používají v balíčků VSIX, typ souboru [Content_Types] .xml je součástí *Open Packaging konvence (OPC)* standard. Další informace najdete v tématu [OPC: Nová standardní pro balení vaše Data](http://go.microsoft.com/fwlink/?LinkID=148207) na webové stránce MSDN.

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují kořenovým prvkem a jeho atributy a podřízené prvky.

### <a name="root-element"></a>Kořenový Element

|Prvek|Popis|
|-------------|-----------------|
|`Types`|Obsahuje podřízené prvky, které zobrazí výčet typů souborů v balíčku souboru VSIX.|

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|`Xmlns`|(Povinné). Umístění schéma používané k tomuto souboru [Content_Types] .xml.|

### <a name="attribute-name-attribute"></a>{Atribut name} Atribut

| Hodnota | Popis |
| - | - |
| http://schemas.openformats.org/package/2006/content-types | Umístění schématu typy obsahu. |

### <a name="child-elements"></a>Podřízené elementy
 `Types` Element může obsahovat libovolný počet `Default` elementy.

|Prvek|Popis|
|-------------|-----------------|
|`Default`|Popisuje typ obsahu v balíčku souboru VSIX. Všechny typy souborů v balíčku musí mít svůj vlastní `Default` elementu.|

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|`Extension`|Přípona názvu souboru souboru v balíčku souboru VSIX.|
|`ContentType`|Popisuje typ obsahu, který je spojen s příponou názvu souboru.|

### <a name="attribute-name-attribute"></a>{Atribut name} Atribut
 Visual Studio rozpoznává následující `ContentType` hodnoty pro přidružený `Extension` typy.

|Linka|ContentType|
|---------------|-----------------|
|TXT|text/plain|
|pkgdef|text/plain|
|xml|text/xml|
|vsixmanifest|text/xml|
|htm nebo html|text/html|
|rtf|aplikace/rtf|
|pdf|aplikace/pdf|
|GIF|image/gif|
|JPG nebo jpeg|image/jpg|
|TIFF|Image/tiff|
|vsix|aplikace/zip|
|zip|aplikace/zip|
|knihovny DLL|application/octet-stream|
|všechny ostatní typy souborů|application/octet-stream|

## <a name="example"></a>Příklad

### <a name="description"></a>Popis
 Následujícího souboru [Content_Types] .xml popisuje typického balíčku VSIX.

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
- [Anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md)
- [Referenční dokumentace schématu 1.0 rozšíření VSIX](https://msdn.microsoft.com/library/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)
- [OPC: Nový Standard pro vytváření balíčků dat](http://go.microsoft.com/fwlink/?LinkID=148207)