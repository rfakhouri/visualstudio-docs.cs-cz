---
title: Migrace registrace třídy 64-bit ladicí program COM | Microsoft Docs
ms.custom: ''
ms.date: 11/10/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 45cfcee6-7a68-4d4f-b3f6-e2d8a0fa066a
author: gregg-miskelly
ms.author: greggm
manager: douge
ms.workload:
- greggm
ms.openlocfilehash: 28516038170dd34028d11bf9a070cf265ecfd830
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31140443"
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
