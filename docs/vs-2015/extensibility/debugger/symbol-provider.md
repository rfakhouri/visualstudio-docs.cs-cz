---
title: Symbol poskytovatele | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- symbol handler
- debugging [Debugging SDK], symbol handler
ms.assetid: 5fce651b-fead-4418-81b0-a011df7644ab
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f09fbe350afff983bb5fefe880104201441430c3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667186"
---
# <a name="symbol-provider"></a>Poskytovatel symbolů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [poskytovatel symbolů](https://docs.microsoft.com/visualstudio/extensibility/debugger/symbol-provider).  
  
Implementace Chyba při vyhodnocování výrazu musí přístup k symbolické ladicí informace generovaný kompilátorem jazyka, aby bylo možné vyhodnocovat proměnné a výrazy. Dělá to tak spotřebovává rozhraní poskytovatele symbolů (SP), taky jako obslužné rutiny symbolů.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] poskytuje aktualizace Service packu pro spravovaný kód, jakož i nativní kód použití formátu souborů symbolů databáze programu (PDB). Pokud není silné nutné pro váš program používat symboly, které jsou uložené ve vlastním formátu, je doporučeno používat aktualizace Service packu poskytnutých [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="implementation-notes"></a>Poznámky k implementaci  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Ladicími stroji se očekávají, že si promluvit se aktualizace Service packu pomocí rozhraní Common Language Runtime (CLR). V důsledku toho SP, která bude práce s moduly ladění sady Visual Studio musí podporovat CLR. Úplný seznam všech CLR ladění v rozhraní najdete v debugref.doc, která je součástí sady [!INCLUDE[winsdklong](../../includes/winsdklong-md.md)].  
  
 Pokud vaše SP pracovat pouze s vlastního ladicího stroje, můžete implementovat SP, která je vhodná v závislosti na potřebách vaší ladicí stroj.  
  
## <a name="see-also"></a>Viz také  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)

