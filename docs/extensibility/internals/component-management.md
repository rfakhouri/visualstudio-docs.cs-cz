---
title: Správa komponent | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- installation [Visual Studio SDK], components
- installation [Visual Studio SDK], file management
ms.assetid: 029bffa2-6841-4caa-a41a-442467e1aedc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 477079cdb0349b2299b5cb829770800a4930958d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66310016"
---
# <a name="component-management"></a>Správa komponent
Jednotky úloh v instalačním programu sady Windows se označují jako součásti Instalační služby systému Windows (říká se jim WICs nebo pouze komponenty). Identifikátor GUID identifikuje každý WIC, což je základní jednotkou instalace a pro nastavení, která pomocí Instalační služby systému Windows pro počítání odkazů.

 I když několik produktů slouží k vytvoření balíčku VSPackage instalační program, tento postup předpokládá použití Instalační služby systému Windows (*MSI*) soubory. Při vytváření instalační program, musíte správně spravovat nasazení souborů tak, aby správné počítání se stane po celou dobu. V důsledku toho různé verze produktu nebude rušit nebo rozdělit mezi sebou v kombinaci instalace a odinstalace scénáře.

 V instalačním programu Windows počítání odkazů dochází na úrovni součásti. Musíte pečlivě uspořádání prostředků – soubory, položky registru a tak dále, do komponenty. Existují další úrovně organizace, jako jsou moduly, funkce a produkty –, které mohou pomoci v různých scénářích. Další informace najdete v tématu [Instalační služby systému Windows Základy](../../extensibility/internals/windows-installer-basics.md).

## <a name="guidelines-of-authoring-setup-for-side-by-side-installation"></a>Pokyny k vytváření nastavení pro instalaci vedle sebe

- Autor soubory a klíče registru, které jsou odkazy sdíleny mezi verzí do jejich vlastních složek.

     To umožňuje snadno je můžou využívat v budoucí verzi. Například knihovny typů, které jsou registrovány globálně, přípony souborů, další položky zaregistrované v **HKEY_CLASSES_ROOT**, a tak dále.

- Sdílené součásti pro seskupení samostatné slučovací moduly.

     Tato strategie pomáhá Autor správně pro instalaci vedle sebe v budoucnu.

- Nainstalujte sdíleným souborům a klíčům registru pomocí stejné komponenty Instalační služby systému Windows ve verzích.

     Pokud používáte jiné součásti, soubory a položky registru jsou odinstalovat, pokud jeden označené verzí balíčku VSPackage je odinstalována, ale jiné VSPackage je nainstalovaná.

- Nekombinujte čísly verzí a sdílené položky pod stejnou komponentou.

     To znemožňuje nainstalovat do globální umístění a verzované položky, které chcete izolované umístění sdílené položky.

- Není nutné klíče sdíleného registru, které odkazují na soubory označené verzí.

     Pokud tak učiníte, při instalaci jinou verzí balíčku VSPackage se přepíše sdílené klíče. Po odebrání druhou verzi souboru, ke kterému bude ukazovat klíč je pryč.

## <a name="see-also"></a>Viz také:
- [Výběr mezi sdíleným a verzovaným rozšířením VSPackages](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)
- [Scénáře instalace balíčku VSPackage](../../extensibility/internals/vspackage-setup-scenarios.md)