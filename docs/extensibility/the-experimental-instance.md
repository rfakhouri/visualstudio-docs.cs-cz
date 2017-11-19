---
title: "Experimentální instanci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- experimental builds
- VSPackages, experimental builds
- VSIP, experimental builds
ms.assetid: ead0df4e-6f88-4b42-9297-581b7902f050
caps.latest.revision: "36"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2de242ed974716b0ba00918d30bc2679a36420fc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="the-experimental-instance"></a>Experimentální instanci
K ochraně vývojového prostředí sady Visual Studio z netestované aplikací, které mohou změnit, VSSDK poskytuje experimentální prostor, který můžete vyzkoušet. Vývoj nových aplikací pomocí sady Visual Studio jako obvykle, ale můžete spustit pomocí této experimentální instance.  
  
 Každá aplikace, který má balíčku VSIX spustí experimentální instanci sady Visual Studio v režimu ladění.  
  
 Pokud chcete spustit experimentální instanci sady Visual Studio mimo konkrétní řešení, spusťte následující příkaz v příkazovém okně:  
  
 "*\<Cesta instalace sady visual studio >*\Common7\IDE\devenv.exe" RootSuffix Exp  
  
> [!NOTE]
>  Experimentální instanci je zapsán do registru pod `<version number>Exp` a `<version number>Exp_Config` uzly. Je třeba oblasti experimentální registru Visual Studio 2015  
>   
>  `HKCU\Software\Microsoft\VisualStudio\14.0Exp`a`HKCU\Software\Microsoft\VisualStudio\14.0Exp_Config`  
  
 Doporučujeme při vývoji ji spustit rozšíření v experimentální instanci. Při nasazení rozšíření, spustí se v instanci vývoj. Další informace o registraci aplikací najdete v tématu [registrace VSPackages](../extensibility/internals/registering-vspackages.md).