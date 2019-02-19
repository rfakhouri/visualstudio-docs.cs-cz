---
title: -Updateconfiguration (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9e058d18c0a7c6d1d3b26a5b379c308d26f790ca
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54783158"
---
# <a name="updateconfiguration-devenvexe"></a>/ Updateconfiguration (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
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
 [Přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
