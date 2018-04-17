---
title: Resolvekeysource – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b5ecfd4785e9e7ef34835eaa9c1b150d6716bb4c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="resolvekeysource-task"></a>ResolveKeySource – úloha
Určuje zdroj klíče silným názvem.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `ResolveKeySource` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AutoClosePasswordPromptShow`|Volitelné `Int32` parametr.<br /><br /> Získá nebo nastaví množství času, v sekundách, k zobrazení počtu si zprávu.|  
|`AutoClosePasswordPromptTimeout`|Volitelné `Int32` parametr.<br /><br /> Získá nebo nastaví množství času, v sekundách, po kterou čekat před jeho zavřením výzva dialogové okno heslo.|  
|`CertificateFile`|Volitelné `String` parametr.<br /><br /> Získá nebo nastaví cestu k souboru certifikátu.|  
|`CertificateThumbprint`|Volitelné `String` parametr.<br /><br /> Získá nebo nastaví kryptografický otisk certifikátu.|  
|`KeyFile`|Volitelné `String` parametr.<br /><br /> Získá nebo nastaví cestu k souboru klíče.|  
|`ResolvedKeyContainer`|Volitelné `String` výstupní parametr.<br /><br /> Získá nebo nastaví přeložit kontejner klíčů.|  
|`ResolvedKeyFile`|Volitelné `String` výstupní parametr.<br /><br /> Získá nebo nastaví přeložit soubor klíče.|  
|`ResolvedThumbprint`|Volitelné `String` výstupní parametr.<br /><br /> Získá nebo nastaví kryptografický otisk certifikátu vyřešený.|  
|`ShowImportDialogDespitePreviousFailures`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, zobrazit dialogové okno importu i v případě selhání předchozí.|  
|`SuppressAutoClosePasswordPrompt`|Volitelné `Boolean` parametr.<br /><br /> Získá nebo nastaví logickou hodnotu, která určuje, zda výzva dialogové okno heslo by nemělo automatickým ukončením.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)