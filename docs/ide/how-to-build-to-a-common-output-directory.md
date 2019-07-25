---
title: 'Postupy: Sestavení do společného výstupního adresáře'
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- output directory
- builds [Visual Studio], common directory
- common directory
ms.assetid: 1fcc2c48-07cb-4c4f-9556-36945e7dfc4e
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a1e669789d2117b4bd2ee550dfffb147e46620c4
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416746"
---
# <a name="how-to-build-to-a-common-output-directory"></a>Postupy: Sestavení do společného výstupního adresáře

Ve výchozím nastavení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sestaví každý projekt v řešení ve vlastní složce v rámci řešení. Můžete změnit výstupní cesty k sestavení vašich projektů, aby bylo možné umístit všechny výstupy do stejné složky.

## <a name="to-place-all-solution-outputs-in-a-common-directory"></a>Vložení všech výstupů řešení do společného adresáře

1. Klikněte na jeden projekt v řešení.

2. V nabídce **projekt** klikněte na příkaz **vlastnosti**.

3. V závislosti na typu projektu klikněte na kartu **kompilovat** nebo na kartu **sestavení** a nastavte **výstupní cestu** ke složce, která se má použít pro všechny projekty v řešení.

4. Opakujte kroky 1-3 pro všechny projekty v řešení.

## <a name="see-also"></a>Viz také:

- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)
- [Postupy: Změna výstupního adresáře sestavení](../ide/how-to-change-the-build-output-directory.md)