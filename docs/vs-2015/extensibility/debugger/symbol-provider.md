---
title: Symbol poskytovatele | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- symbol handler
- debugging [Debugging SDK], symbol handler
ms.assetid: 5fce651b-fead-4418-81b0-a011df7644ab
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6af1af9d2e178241fa8a5957e18c1a5333fa4b09
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68178891"
---
# <a name="symbol-provider"></a>Poskytovatel symbolů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Implementace Chyba při vyhodnocování výrazu musí přístup k symbolické ladicí informace generovaný kompilátorem jazyka, aby bylo možné vyhodnocovat proměnné a výrazy. Dělá to tak spotřebovává rozhraní poskytovatele symbolů (SP), taky jako obslužné rutiny symbolů.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] poskytuje aktualizace Service packu pro spravovaný kód, jakož i nativní kód použití formátu souborů symbolů databáze programu (PDB). Pokud není silné nutné pro váš program používat symboly, které jsou uložené ve vlastním formátu, je doporučeno používat aktualizace Service packu poskytnutých [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="implementation-notes"></a>Poznámky k implementaci  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Ladicími stroji se očekávají, že si promluvit se aktualizace Service packu pomocí rozhraní Common Language Runtime (CLR). V důsledku toho SP, která bude práce s moduly ladění sady Visual Studio musí podporovat CLR. Úplný seznam všech CLR ladění v rozhraní najdete v debugref.doc, která je součástí sady [!INCLUDE[winsdklong](../../includes/winsdklong-md.md)].  
  
 Pokud vaše SP pracovat pouze s vlastního ladicího stroje, můžete implementovat SP, která je vhodná v závislosti na potřebách vaší ladicí stroj.  
  
## <a name="see-also"></a>Viz také  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)
