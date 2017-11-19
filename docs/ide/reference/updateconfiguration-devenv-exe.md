---
title: -Updateconfiguration (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93efd5d0e0eb391a164f4997b7ddeedab09b4201
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="updateconfiguration-devenvexe"></a>/ Updateconfiguration (devenv.exe)
Upozorní [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sloučit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] balíčků na systém a kontroly MEF mezipaměti pro všechny změny.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /updateconfiguration  
```  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Tento příkaz spustí automaticky při instalaci balíčku VSIX. Byste měli spustit `devenv.exe /updateconfiguration` po opravy vaše soubory tak, aby [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aktualizuje mezipaměť MEF. Můžete k vyhodnocení, zda vaše oprava je dostačující.  
  
## <a name="example"></a>Příklad  
 Následující příkazový řádek příčiny [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sloučit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] balíčků na systém a kontroly MEF mezipaměti pro všechny změny.  
  
```  
Devenv.exe /updateconfiguration  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)   
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)