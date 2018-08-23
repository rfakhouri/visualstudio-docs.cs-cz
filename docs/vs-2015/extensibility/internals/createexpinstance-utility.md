---
title: Nástroj CreateExpInstance | Dokumentace Microsoftu
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
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9b08ba5ac68a09f6c44937634375add3065e5e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666757"
---
# <a name="createexpinstance-utility"></a>Nástroj CreateExpInstance
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [nástroj CreateExpInstance](https://docs.microsoft.com/visualstudio/extensibility/internals/createexpinstance-utility).  
  
Použijte nástroj CreateExpInstance k vytvoření, obnovení, nebo odstranit experimentální instanci sady Visual Studio. Experimentální instanci slouží k ladění a testování rozšíření sady Visual Studio beze změny základní produkt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix  
```  
  
#### <a name="parameters"></a>Parametry  
 / Vytvoření  
 Vytvoří experimentální instanci aplikace.  
  
 / Reset  
 Odstraní experimentální instanci a pak vytvoří nový.  
  
 /Clean  
 Odstraní experimentální instanci aplikace.  
  
 / VSInstance  
 Název adresáře, který obsahuje základní instance sady Visual Studio ke kopírování.  
  
 / RootSuffix  
 Přípona pro připojení k názvu adresáře experimentální instanci aplikace.  
  
## <a name="remarks"></a>Poznámky  
 Při práci na rozšíření sady Visual Studio, můžete stisknutím klávesy F5 spusťte výchozí experimentální instanci a nainstalujte aktuální rozšíření. Pokud je k dispozici žádná experimentální instance, vytvoří Visual Studio, pokud má výchozí nastavení.  
  
 Výchozí umístění experimentální instanci aplikace závisí na číslo verze sady Visual Studio. Například pro sadu Visual Studio 2015 je umístění %localappdata%\Microsoft\VisualStudio\14.0Exp\ všechny soubory v umístění adresáře jsou považovány za součást této instance. Všechny další experimentální instance nebude načten pomocí sady Visual Studio, pokud název adresáře se změní na výchozí umístění.  
  
 Visual Studio nepřistupuje k systémovým registrem při otevření experimentální instanci aplikace. Tím se liší od předchozí verze sady Visual Studio, který používá experimentální verzi podregistr registru.  
  
 Nástroj CreateExpInstance nahrazuje nástroj VsRegEx.  
  
 Následující příklad Resetuje výchozí experimentální instanci sady Visual Studio.  
  
 **/ Reset CreateExpInstance.exe /VSInstance = 14.0 /RootSuffix = Exp**  
  
## <a name="see-also"></a>Viz také  
 [Vydání produktu](../../misc/releasing-a-visual-studio-integration-product.md)

