---
title: Resolvekeysource – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveKeySource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveKeySource task [MSBuild]
- MSBuild, ResolveKeySource task
ms.assetid: 449f06c2-e9aa-4236-ab1e-c45c25452b2e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 123c45ed23743335a1c4db2000dd241cb92ce291
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62810633"
---
# <a name="resolvekeysource-task"></a>ResolveKeySource – úloha
Určuje zdroj klíče silného názvu.

## <a name="task-parameters"></a>Parametry úlohy
 Následující tabulka popisuje parametry `ResolveKeySource` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`AutoClosePasswordPromptShow`|Volitelné `Int32` parametru.<br /><br /> Získá nebo nastaví dobu, během několika sekund, chcete-li zobrazit počet si zprávu.|
|`AutoClosePasswordPromptTimeout`|Volitelné `Int32` parametru.<br /><br /> Získá nebo nastaví dobu, během několika sekund se má čekat před zavřením dialogové okno Příkazový řádek heslo.|
|`CertificateFile`|Volitelné `String` parametru.<br /><br /> Získá nebo nastaví cestu k souboru certifikátu.|
|`CertificateThumbprint`|Volitelné `String` parametru.<br /><br /> Získá nebo nastaví kryptografický otisk certifikátu.|
|`KeyFile`|Volitelné `String` parametru.<br /><br /> Získá nebo nastaví cestu k souboru klíče.|
|`ResolvedKeyContainer`|Volitelné `String` výstupní parametr.<br /><br /> Získá nebo nastaví přeložit kontejneru klíčů.|
|`ResolvedKeyFile`|Volitelné `String` výstupní parametr.<br /><br /> Získá nebo nastaví přeložit soubor klíče.|
|`ResolvedThumbprint`|Volitelné `String` výstupní parametr.<br /><br /> Získá nebo nastaví kryptografický otisk certifikátu přeložit.|
|`ShowImportDialogDespitePreviousFailures`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, zobrazit dialogové okno importu bez ohledu na předchozí chyby.|
|`SuppressAutoClosePasswordPrompt`|Volitelné `Boolean` parametru.<br /><br /> Získá nebo nastaví logickou hodnotu, která určuje, zda dialogové okno Příkazový řádek heslo by neměl automatickým ukončením.|

## <a name="remarks"></a>Poznámky
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)