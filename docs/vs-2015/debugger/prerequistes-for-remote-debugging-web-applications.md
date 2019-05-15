---
title: Předpoklady pro vzdálené ladění webových aplikací | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c13cfdeb90fae554479c7dc8a68261f40bc4cfc6
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65690102"
---
# <a name="prerequistes-for-remote-debugging-web-applications"></a>Předpoklady pro vzdálené ladění webových aplikací
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

S [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ladicího programu, můžete ladit webové aplikace transparentně na místním počítači nebo na vzdálený server. To znamená, že funkce ladicího programu stejným způsobem a umožňuje použití stejných funkcí na oba počítače. Pro vzdálené ladění fungovala správně, ale existují některé požadavky.  
  
- [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] komponenty vzdáleného ladění musí být nainstalován na serveru, který chcete ladit. Další informace najdete v tématu [nastavení do vzdáleného ladění](https://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).  
  
- Ve výchozím nastavení [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces spuštěn jako proces ASPNET uživatele. V důsledku toho musí mít oprávnění správce na počítači kde [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] spuštění pro ladění. Název [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces se liší podle scénáře ladění a verze služby IIS. Další informace najdete v tématu [jak: Hledání názvu procesu ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací ASP.NET a AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Požadavky na systém](../debugger/aspnet-debugging-system-requirements.md)
