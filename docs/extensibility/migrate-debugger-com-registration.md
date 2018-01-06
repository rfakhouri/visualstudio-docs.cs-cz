---
title: "Migrace registrace třídy 64-bit ladicí program COM | Microsoft Docs"
ms.custom: 
ms.date: 11/10/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45cfcee6-7a68-4d4f-b3f6-e2d8a0fa066a
caps.latest.revision: "1"
author: gregg-miskelly
ms.author: greggm
manager: ghogen
ms.workload: greggm
ms.openlocfilehash: 737c970555fce8f3cdac118421eddb09f52d7c53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="migrate-64-bit-debugger-com-class-registration"></a>Migrace 64-bit ladicí program registrace třídy COM

Pro ladicí program rozšíření, která zaregistrovat třídy COM v HKEY_CLASSES_ROOT (pomocí modul regasm, regsvr32, nebo přímo zápis do registru) a načtena do msvsmon.exe (vzdáleného ladicího programu) je možné zajistit tato registrace k msvsmon bez nutnosti zapsat do HKEY_CLASSES_ROOT. To má vliv na starší verze vyhodnocovače výrazů ladicí program rozhraní .NET nebo ladění moduly, které jsou nakonfigurovány na spouštění v procesu msvsmon.exe.

## <a name="msvsmon-comclass-def"></a>msvsmon-comclass-def

Pokud chcete použít tento postup, přidá soubor *.msvsmon. comclass def.json vedle msvsmon (InstallDir:\Common7\IDE\Remote Debugger\x64).

Tady je příklad msvsmon-comclass-def souboru, který registruje jeden spravovaný a jeden nativních tříd:

Název souboru: MyCompany.MyExample.msvsmon-comclass-def.json

```json
{
  "managedCOMClasses": [
    {
      "clsid": "{C9F48B25-36ED-4B22-8210-98BC5BE4D1E7}",
      "assemblyName": "MyCompany.MyAssembly",
      "className": "MyCompany.MyNamespace.MyClass"
    }
  ],
  "nativeCOMClasses": [
    {
      "clsid": "{42A476E9-8FA7-44D5-ADFE-216AD371EEC9}",
      "dllPath": "MyExample.dll"
    }
  ]
}
```
