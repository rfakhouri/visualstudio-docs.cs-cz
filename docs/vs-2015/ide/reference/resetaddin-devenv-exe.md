---
title: -ResetAddin (devenv.exe) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: df5fe62efd783551a483853543ddb30312e64c65
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49213665"
---
# <a name="resetaddin-devenvexe"></a>/ResetAddin (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Odstraní příkazy a příkaz rozhraní přidružené k zadaným Add-in.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /ResetAddin AddIn  
```  
  
## <a name="arguments"></a>Arguments  
 `AddIn`  
 Volitelné. Název příkazu doplňku.  
  
## <a name="remarks"></a>Poznámky  
 Výchozí název příkazu doplňku je roven  *\<AddInSolutionName >*. Připojit *.\< AddInSolutionName >* a zobrazí se v Connect.cs jako `commandName` parametr `Exec` metody. Můžete také ověřit název příkazu tak, že začnete zadávat název doplňku do okna Příkazy v sadě Visual Studio a pomocí technologie Intellisense doplníte zbytek.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu spustí Visual Studio a brání `MyAddin` doplňku v běhu při spuštění.  
  
```  
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)



