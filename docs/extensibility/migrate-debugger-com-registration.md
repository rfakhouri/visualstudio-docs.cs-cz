---
title: Migrace registrace třídy 64-bit ladicího programu modelu COM | Dokumentace Microsoftu
ms.date: 11/10/2016
ms.topic: conceptual
ms.assetid: 45cfcee6-7a68-4d4f-b3f6-e2d8a0fa066a
author: gregg-miskelly
ms.author: greggm
manager: jillfra
ms.workload:
- greggm
ms.openlocfilehash: 74fbb959f8272be001aad8a576724d5eb1ad6157
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62433692"
---
# <a name="migrate-64-bit-debugger-com-class-registration"></a>Migrace 64bitové ladicí program registrace třídy modelu COM

Pro rozšíření ladicího programu, které registrace modelu COM třídy v registru HKEY_CLASSES_ROOT pomocí regasm regsvr32, nebo přímo na zápis do registru a načtena do *msvsmon.exe* (vzdálený ladicí program), je teď možné poskytnout to se aniž byste museli napsat HKEY_CLASSES_ROOT msvsmon registrace. To má vliv na starší verze vyhodnocovače výrazů ladicího programu .NET nebo ladicí stroj, které jsou nakonfigurovány k načtení v *msvsmon.exe* procesu.

## <a name="msvsmon-comclass-def"></a>msvsmon-comclass-def

Chcete-li použít tuto techniku, přidejte  **.msvsmon. comclass def.json* souboru vedle msvsmon (InstallDir:* \Common7\IDE\Remote Debugger\x64*).

Tady je příklad souboru msvsmon. comclass def, která se registruje spravuje a jeden nativních tříd:

Název souboru: *MyCompany.MyExample.msvsmon-comclass-def.json*

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
