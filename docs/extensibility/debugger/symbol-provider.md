---
title: "Symbolů zprostředkovatele | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- symbol handler
- debugging [Debugging SDK], symbol handler
ms.assetid: 5fce651b-fead-4418-81b0-a011df7644ab
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e0f01e10050fcbdb5cf27390464ae6b8b3e62d64
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="symbol-provider"></a>Symbol zprostředkovatele
Implementace vyhodnocování výrazu musí přístup k symbolické ladicí informace generované kompilátor jazyka, aby bylo možné vyhodnotit proměnné a výrazy. Dělá to pomocí využívání rozhraní symbol zprostředkovatele (SP), označované taky jako obslužná rutina symbol.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]poskytuje aktualizace Service Pack pro spravovaný kód a také nativní kód pomocí formát souboru databáze programu (PDB) symbol. Pokud je silné potřebují k aplikaci použít symboly, které jsou uložené ve vlastním formátu, je doporučeno používat SP poskytl [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="implementation-notes"></a>Poznámky k implementaci  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Moduly ladění očekávat komunikovat s aktualizace Service Pack pomocí rozhraní Common Language Runtime (CLR). V důsledku toho SP, který bude práce s moduly ladění Visual Studio musí podporovat modulu CLR. Úplný seznam všech CLR ladění v rozhraní najdete v debugref.doc, která je součástí služby [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)].  
  
 Pokud vaše SP bude pracovat pouze s modulem vaše vlastní ladění, můžete implementovat SP podle potřeby v závislosti na potřebách vaší ladění modulu.  
  
## <a name="see-also"></a>Viz také  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)