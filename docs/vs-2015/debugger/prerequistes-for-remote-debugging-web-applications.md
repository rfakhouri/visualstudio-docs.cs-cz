---
title: Předpoklady pro vzdálené ladění webových aplikací | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications, remote servers
- remote debugging, prerequisites
- remote servers, debugging Web applications
ms.assetid: 1cd777b5-6d20-4ca6-a0df-51653b118469
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 197a6e9b433173f1de13e3506db79e7edf53bade
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668476"
---
# <a name="prerequistes-for-remote-debugging-web-applications"></a>Předpoklady pro vzdálené ladění webových aplikací
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [předpoklady pro vzdálené ladění webových aplikací](https://docs.microsoft.com/visualstudio/debugger/prerequistes-for-remote-debugging-web-applications).  
  
S [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ladicího programu, můžete ladit webové aplikace transparentně na místním počítači nebo na vzdálený server. To znamená, že funkce ladicího programu stejným způsobem a umožňuje použití stejných funkcí na oba počítače. Pro vzdálené ladění fungovala správně, ale existují některé požadavky.  
  
-   [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] komponenty vzdáleného ladění musí být nainstalován na serveru, který chcete ladit. Další informace najdete v tématu [nastavení do vzdáleného ladění](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).  
  
-   Ve výchozím nastavení [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces spuštěn jako proces ASPNET uživatele. V důsledku toho musí mít oprávnění správce na počítači kde [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] spuštění pro ladění. Název [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces se liší podle scénáře ladění a verze služby IIS. Další informace najdete v tématu [postupy: hledání názvu procesu ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací ASP.NET a AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Požadavky na systém](../debugger/aspnet-debugging-system-requirements.md)



