---
title: "Resolvekeysource – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#ResolveKeySource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveKeySource task [MSBuild]
- MSBuild, ResolveKeySource task
ms.assetid: 449f06c2-e9aa-4236-ab1e-c45c25452b2e
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 49bc9f428eb4c214232a8ca3a59749e355cf8ba6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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