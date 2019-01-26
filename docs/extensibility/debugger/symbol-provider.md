---
title: Symbol poskytovatele | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- symbol handler
- debugging [Debugging SDK], symbol handler
ms.assetid: 5fce651b-fead-4418-81b0-a011df7644ab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ed25959cd6afa7232555757e358a99836d93924b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54981477"
---
# <a name="symbol-provider"></a>Poskytovatel symbolů
Implementace Chyba při vyhodnocování výrazu musí přístup k symbolické ladicí informace generovaný kompilátorem jazyka, aby bylo možné vyhodnocovat proměnné a výrazy. Dělá to tak spotřebovává rozhraní poskytovatele symbolů (SP), taky jako obslužné rutiny symbolů.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] poskytuje aktualizace Service packu pro spravovaný kód, jakož i nativní kód použití formátu souborů symbolů databáze programu (PDB). Pokud není silné nutné pro váš program používat symboly, které jsou uložené ve vlastním formátu, je doporučeno používat aktualizace Service packu poskytnutých [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="implementation-notes"></a>Poznámky k implementaci  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Ladicími stroji se očekávají, že si promluvit se aktualizace Service packu pomocí rozhraní Common Language Runtime (CLR). V důsledku toho SP, která bude práce s moduly ladění sady Visual Studio musí podporovat CLR. Úplný seznam všech CLR ladění v rozhraní najdete v debugref.doc, která je součástí sady [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)].  
  
 Pokud vaše SP pracovat pouze s vlastního ladicího stroje, můžete implementovat SP, která je vhodná v závislosti na potřebách vaší ladicí stroj.  
  
## <a name="see-also"></a>Viz také:  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)