---
title: "– Příkaz (devenv.exe) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6f7f2914b59025d3cf1dc82d43191f43ec7b0115
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
Provede zadaný příkaz po spuštění [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /command CommandName  
```  
  
## <a name="arguments"></a>Arguments  
 `CommandName`  
 Požadováno. Úplný název [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] příkaz nebo jeho alias uzavřena v uvozovkách. Další informace o příkazu a alias syntaxi najdete v tématu [příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md).  
  
## <a name="remarks"></a>Poznámky  
 Po dokončení spuštění prostředí IDE provede příkaz s názvem. Pokud chcete použít tento přepínač, rozhraní IDE nejsou zobrazeny [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] – úvodní stránka při spuštění.  
  
 Pokud doplněk zpřístupní příkaz, můžete tento přepínač pro spuštění add-in z příkazového řádku. Další informace najdete v tématu [postupy: řízení doplňky s použitím správce Add-In](http://msdn.microsoft.com/Library/4f60444a-cb48-4cdb-8df4-941f6419aeeb).  
  
## <a name="example"></a>Příklad  
 Tento příklad spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a automaticky spustí makro otevřených souborů oblíbených položek.  
  
```  
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)