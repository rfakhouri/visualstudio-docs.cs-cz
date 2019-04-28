---
title: Vytvoříte balíček rozšíření pomocí šablony položky balíčku rozšíření | Dokumentace Microsoftu
ms.date: 07/27/2018
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - extensions
ms.assetid: 5388EEBA-211D-4114-8CD9-70C899919F7E
author: gregvanl
ms.author: gregvanl
manager: Meng
ms.workload:
- vssdk
ms.openlocfilehash: 7899a096bb2a56e93ea55a4ba0a17cde272bd615
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62950951"
---
# <a name="walkthrough-create-an-extension-pack"></a>Návod: Vytvoření balíčku rozšíření

Balíček rozšíření pro je sada rozšíření, které mohou být nainstalovány společně. Balíčky rozšíření umožňují snadno sdílet vaše oblíbená rozšíření s ostatními uživateli nebo sady sadu rozšíření pro konkrétní scénář.

## <a name="prerequisites"></a>Požadavky

Spouští se v sadě Visual Studio 2015, Visual Studio SDK je zahrnuté jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

Balíček rozšíření funkce je k dispozici od verze Visual Studio 15.8 ve verzi Preview 2.

## <a name="create-an-extension-with-an-extension-pack-item-template"></a>Vytváření rozšíření pomocí šablony položky balíček rozšíření

Balíček rozšíření pro položky šablona vytvoří balíček rozšíření pro sadu rozšíření, které mohou být nainstalovány společně.

1. V **nový projekt** dialogové okno, vyhledejte "vsix" a vyberte **projekt VSIX**. Pro **název projektu**, typ "Balíček rozšíření pro Test". Vyberte **Vytvořit**.

2. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat** > **nová položka**. Přejděte do aplikace Visual C# **rozšiřitelnost** uzel a vyberte možnost **balíček rozšíření**. Ponechte výchozí název souboru (ExtensionPack1.cs).

3. Při přidání ExtensionPack1.vsext souboru, který obsahuje následující kód

   ```json
   {
    "id": "ExtensionPack1",
    "name": "ExtensionPack1",
    "description": "Read about creating extension packs at https://aka.ms/vsextpack",
    "version": "1.0.0.0",
    "extensions": [  // List of extensions that are included in the Extension Pack.
      {
        "vsixId": "41858b2d-ff0b-4a43-80b0-f1b2d6084935", // The vsix id of the extension you want to   include.
        "name": "AlignAssignments"
      },
      {
          "vsixId": "42374550-426a-400e-96f9-237682e8dea6",
        "name": "CopyAsHtml"
      }
    ]
   }
   ```

4. Vsixid rozšíření, které chcete zahrnout do balíčku rozšíření můžete najít na [Visual Studio Marketplace](https://marketplace.visualstudio.com/). Najít rozšíření, které chcete zahrnout, a klikněte na **ID kopie**. Můžete aktualizovat existující **vsixId** v uvedeném souboru nebo jiného rozšíření přidat do seznamu.

    ![Zkopírujte VsixId z Marketplace](media/vsixid-marketplace.png)

5. Sestavte projekt a nahrát rozšíření na webu Marketplace. Zobrazit [publikování rozšíření sady Visual Studio](../extensibility/walkthrough-publishing-a-visual-studio-extension.md).

> [!NOTE]
> Balíček rozšíření pro můžete nainstalovat pouze rozšíření, které jsou k dispozici na [Visual Studio Marketplace](https://marketplace.visualstudio.com/) nebo [privátní Galerie](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md).

## <a name="install-the-extension-pack-from-the-visual-studio-marketplace"></a>Nainstalovat balíček rozšíření z Visual Studio Marketplace

Teď, když se publikuje rozšíření, nainstalujte ho v sadě Visual Studio a ho vyzkoušeli.

::: moniker range="vs-2017"

1. V sadě Visual Studio na **nástroje** nabídky, klikněte na tlačítko **rozšíření a aktualizace**.

::: moniker-end

::: moniker range=">=vs-2019"

1. V sadě Visual Studio na **rozšíření** nabídky, klikněte na tlačítko **spravovaných rozšíření**.

::: moniker-end

2. Klikněte na tlačítko **Online** a vyhledejte "Balíček rozšíření pro Test".

3. Klikněte na tlačítko **Stáhnout**. Rozšíření a její seznam přípon, které jsou součástí balíčku rozšíření se pak být naplánovaná instalace.

4. Následuje ukázkový balíček rozšíření pro stažení zobrazení **spravovat rozšíření** dialogového okna. Pokud chcete nainstalovat jenom některé z zahrnutých rozšíření v balíčku rozšíření, můžete upravit seznam rozšíření v **naplánované pro instalaci**.

    ![Stáhněte si balíček rozšíření z Marketplace](media/vside-extensionpack.png)

5. K dokončení instalace, ukončete všechny instance sady Visual Studio.

## <a name="remove-the-extension"></a>Odebrat rozšíření

Odebrat rozšíření z počítače:

::: moniker range="vs-2017"

1. V sadě Visual Studio na **nástroje** nabídky, klikněte na tlačítko **rozšíření a aktualizace**.

::: moniker-end

::: moniker range=">=vs-2019"

1. V sadě Visual Studio na **rozšíření** nabídky, klikněte na tlačítko **spravovaných rozšíření**.

::: moniker-end

2. Vyberte **balíček rozšíření pro Test** a potom klikněte na tlačítko **odinstalovat**. Rozšíření a její seznam přípon, které jsou součástí balíčku rozšíření se pak být naplánovaná odinstalace.

3. K dokončení odinstalace, zavřete všechny instance sady Visual Studio.
