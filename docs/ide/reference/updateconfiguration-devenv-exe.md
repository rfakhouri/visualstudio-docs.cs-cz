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
ms.workload: multiple
ms.openlocfilehash: 0ec3bfc47829bce2fe5ad836c970cb28f8a1294e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)