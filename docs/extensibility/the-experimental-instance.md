---
title: Experimentální instanci | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- experimental builds
- VSPackages, experimental builds
- VSIP, experimental builds
ms.assetid: ead0df4e-6f88-4b42-9297-581b7902f050
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8c4aa7e8e74ccb8f31dc2320192cf088b5391678
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685115"
---
# <a name="the-experimental-instance"></a>Experimentální instance
K ochraně vašeho vývojového prostředí sady Visual Studio z neověřeného aplikací, které mohou změnit, VSSDK místo experimentální, který vám pomůže experimentovat. Při vývoji nových aplikací pomocí sady Visual Studio jako obvykle, ale spouštíte je pomocí tento experimentální instanci.

 Každá aplikace, která obsahuje balíček VSIX spustí experimentální instanci sady Visual Studio v režimu ladění.

 Pokud chcete spustit experimentální instanci sady Visual Studio mimo konkrétní řešení, spusťte následující příkaz v příkazovém okně:

 "*\<Cestu instalace sady visual studio >* \Common7\IDE\devenv.exe" RootSuffix Exp

> [!NOTE]
>  Experimentální instanci jsou zapsána do registru pod `<version number>Exp` a `<version number>Exp_Config` uzly. Je třeba oblasti experimentální registru Visual Studio 2015
>
>  `HKCU\Software\Microsoft\VisualStudio\14.0Exp` a `HKCU\Software\Microsoft\VisualStudio\14.0Exp_Config`

 Doporučujeme při vývoji se spustit rozšíření v experimentální instanci aplikace. Při nasazení rozšíření, poběží v instanci vývoje. Další informace o registraci aplikace najdete v tématu [registrace rozšíření VSPackages](../extensibility/internals/registering-vspackages.md).