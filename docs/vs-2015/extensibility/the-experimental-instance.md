---
title: Experimentální instanci | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- experimental builds
- VSPackages, experimental builds
- VSIP, experimental builds
ms.assetid: ead0df4e-6f88-4b42-9297-581b7902f050
caps.latest.revision: 37
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 907b90f60ad2167b64e5a4ca8ff160190c625313
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54760974"
---
# <a name="the-experimental-instance"></a>Experimentální instance
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

K ochraně vašeho vývojového prostředí sady Visual Studio z neověřeného aplikací, které mohou změnit, VSSDK místo experimentální, který vám pomůže experimentovat. Při vývoji nových aplikací pomocí sady Visual Studio jako obvykle, ale spouštíte je pomocí tento experimentální instanci.  
  
 Každá aplikace, která obsahuje balíček VSIX spustí experimentální instanci sady Visual Studio v režimu ladění.  
  
 Pokud chcete spustit experimentální instanci sady Visual Studio mimo konkrétní řešení, spusťte následující příkaz v příkazovém okně:  
  
 "*\<Cestu instalace sady visual studio >* \Common7\IDE\devenv.exe" RootSuffix Exp  
  
> [!NOTE]
>  Experimentální instanci jsou zapsána do registru pod `<version number>Exp` a `<version number>Exp_Config` uzly. Je třeba oblasti experimentální registru Visual Studio 2015  
>   
>  `HKCU\Software\Microsoft\VisualStudio\14.0Exp` a `HKCU\Software\Microsoft\VisualStudio\14.0Exp_Config`  
  
 Doporučujeme při vývoji se spustit rozšíření v experimentální instanci aplikace. Při nasazení rozšíření, poběží v instanci vývoje. Další informace o registraci aplikace najdete v tématu [registrace rozšíření VSPackages](../extensibility/internals/registering-vspackages.md).
