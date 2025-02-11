---
title: 'Návod: Vytvoření vlastního editoru | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - create
ms.assetid: d090abb6-d99f-4083-a3db-cd16bf81ce7d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eca6bc68accfd5c33e439ddfc5709943be7b549e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66312752"
---
# <a name="walkthrough-create-a-custom-editor"></a>Návod: Vytvoření vlastního editoru
Šablona projektu VSPackage můžete vytvořit jednoduchý vlastní editor v jazyce C++. Šablona projektu VSPackage už nepodporuje projekty jazyka C# nebo Visual Basic. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

## <a name="prerequisites"></a>Požadavky
 Chcete-li postupovat podle tohoto návodu, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="the-visual-studio-package-project-template"></a>Šablona projektu balíček Visual Studio
 Můžete najít šablonu projektu Visual Studio balíček v **nový projekt** dialogového okna v části **rozšíření C++** složky.

### <a name="to-create-a-vspackage-using-the-visual-studio-package-template"></a>Chcete-li vytvořit pomocí šablony sady Visual Studio balíčku VSPackage

1. Vytvořte projekt pomocí šablony Visual Studio balíček.

2. Vyberte **vlastního editoru** možnost a klikněte na tlačítko **Další**. **Možnosti editoru** se zobrazí stránka.

3. Zadejte název v editoru **název editoru** pole. Zadejte příponu souboru, který chcete přidružit v editoru v **přípona souboru** pole. Editor je k dispozici pro soubory s touto příponou. Přípona souboru je zaregistrována pro sadu Visual Studio pouze, ne pro Windows. Zadejte název souboru výchozí pro nové dokumenty vytvořené v editoru v **výchozí název souboru** pole.

4. Klikněte na tlačítko **Dokončit** k vytvoření vašeho balíčku VSPackage v zadané složce.

### <a name="to-test-your-custom-editor"></a>K otestování vlastního editoru

1. Na **souboru** nabídky, přejděte k **nový** a potom klikněte na tlačítko **souboru**.

2. V **nainstalované šablony** podokně **nový soubor** dialogovém okně vyberte soubor šablony a pak ho zadejte je zaregistrovaný.

3. Klikněte na tlačítko **otevřít** k zobrazení a úpravě dokumentu.

     Editor podporuje operace vyjmutí a vložení, najít a nahradit a otevřít a zatížení.

## <a name="see-also"></a>Viz také:
- [Balíčky VSPackage](../extensibility/internals/vspackages.md)