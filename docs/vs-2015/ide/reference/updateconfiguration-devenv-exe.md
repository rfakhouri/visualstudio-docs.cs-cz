---
title: -Updateconfiguration (devenv.exe) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 31fd7f52ad2be89a3e6a40a76948aea0d8cc8bfc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667380"
---
# <a name="updateconfiguration-devenvexe"></a>/ Updateconfiguration (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [- Updateconfiguration (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/updateconfiguration-devenv-exe).  
  
  
Upozorní [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] sloučit [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] mezipaměť balíčků na systém a rozhraní MEF pro všechny změny.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /updateconfiguration  
```  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tento příkaz se spustí automaticky při instalaci balíčku VSIX. Měli byste spustit `devenv.exe /updateconfiguration` po použití dílčích oprav soubory tak, aby [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] aktualizuje mezipaměť MEF. To umožňuje vyhodnotit, jestli je vhodná, jste kód opravili správně.  
  
## <a name="example"></a>Příklad  
 Následující příkazový řádek příčiny [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] sloučit [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] mezipaměť balíčků na systém a rozhraní MEF pro všechny změny.  
  
```  
Devenv.exe /updateconfiguration  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)



