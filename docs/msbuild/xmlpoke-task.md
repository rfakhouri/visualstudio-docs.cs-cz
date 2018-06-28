---
title: Xmlpoke – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31c76ba53e858d9eab41d6579950f47b16f8c9b8
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056352"
---
# <a name="xmlpoke-task"></a>XmlPoke – úloha

Nastaví hodnoty podle specifikace dotaz XPath do souboru XML.

## <a name="parameters"></a>Parametry

 Následující tabulka popisuje parametry `XmlPoke` úloh.
  
|Parametr|Popis|
|---------------|-----------------|
|`Namespaces`|Volitelné `String` parametr.<br /><br /> Určuje obor názvů pro předpony dotaz XPath. `Namespaces` je fragmentu kódu XML skládající se z `Namespace` elementy s atributy `Prefix` a `Uri`. Atribut `Prefix` Určuje předponu pro obor názvů specifikovaný v přidružení `Uri` atribut. Nepoužívejte prázdnou `Prefix`.|
|`Query`|Volitelné `String` parametr.<br /><br /> Určuje dotaz XPath.|
|`Value`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje hodnotu, která má být vložen do zadané cesty.|
|`XmlInputPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje vstup XML jako cestu k souboru.|

## <a name="remarks"></a>Poznámky

 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad

Tady je sample.xml upravit:

```
<Package xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
         xmlns:mp="http://schemas.microsoft.com/appx/2014/phone/manifest"
         xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10" >
<Identity Name="Sample.Product " Publisher="CN=1234" Version="1.0.0.0" />
<mp:PhoneIdentity PhoneProductId="456" PhonePublisherId="0" />
</Package>
```

V tomto příkladu, pokud chcete upravit `/Package/mp:PhoneIdentity/PhonePublisherId`, pak použít

```
<Project>
  <PropertyGroup>
    <Namespace>
        <Namespace Prefix="dn" Uri="http://schemas.microsoft.com/appx/manifest/foundation/windows10" />
        <Namespace Prefix="mp" Uri="http://schemas.microsoft.com/appx/2014/phone/manifest" />
        <Namespace Prefix="uap" Uri="http://schemas.microsoft.com/appx/manifest/uap/windows10" />
    </Namespace>
</PropertyGroup>

<Target Name="Poke">
  <XmlPoke
    XmlInputPath="Sample.xml"
    Value="MyId"
    Query="/dn:Package/mp:PhoneIdentity/@PhoneProductId"
    Namespaces="$(Namespace)"/>
</Target>
</Project>
```

`dn` Zde slouží jako předponu umělé obor názvů pro výchozí obor názvů.

## <a name="see-also"></a>Viz také

 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
