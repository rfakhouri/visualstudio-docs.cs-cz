---
title: Určení výchozí Namespace projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- custom tools, computing default namespace
ms.assetid: 6d890676-7016-458c-8a6a-95cc0a068612
caps.latest.revision: 13
manager: jillfra
ms.openlocfilehash: 0bc5cba2651f447e36491c641e9b0d05f728e5c7
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54791762"
---
# <a name="determining-the-default-namespace-of-a-project"></a>Určení výchozí Namespace projektu
Pro [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], pokud `CustomToolNamespace` je nastavena na vstupní soubor, pak hodnota `CustomToolNamespace` změní hodnotu výchozí obor názvů parametr předán <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> metoda. V opačném případě `wszDefaultNamespace` byl předán parametr `Generate` se vždy rovná kořenového oboru názvů. Další informace o oborech názvů najdete v tématu [klíčová slova Namespace](http://msdn.microsoft.com/library/091a66eb-b10d-4f54-9102-5ac0d4bdb84b).  
  
 [!INCLUDE[csprcs](../includes/csprcs-md.md)] používá obory názvů založené na složce. To znamená obor názvů se skládá z kořenového oboru názvů a názvy složek obsahující vlastní nástroj. Každý název složky je převést na platný identifikátor a všechny názvy oddělte období. Například pokud je vstupní soubor FolderA\FolderB\FolderC\MyInput.txt a kořenový obor názvů se CL9, pak vypočítané výchozí obor názvů by **CL9. FolderA.FolderB.FolderC**.  
  
 Výjimkou z tohoto pravidla vyvolá se v případě řetězec hierarchie obsahuje složka webových odkazů. Například pokud:  
  
- FolderC byly složka webových odkazů, obor názvů by **CL9. FolderC**.  
  
- FolderB byly složka webových odkazů, obor názvů by **CL9. FolderB.FolderC**.  
  
  To znamená že obor názvů používá následující formát:  
  
```  
rootNamespace.webReferenceFolder.containedFolder.containedFolder ...  
```  
  
## <a name="see-also"></a>Viz také  
 [Implementace generátorů tvořených jedním souborem](../extensibility/internals/implementing-single-file-generators.md)   
 [Registrace generátorů tvořených jedním souborem](../extensibility/internals/registering-single-file-generators.md)   
 [Zveřejnění typů pro vizuální návrháře](../extensibility/internals/exposing-types-to-visual-designers.md)