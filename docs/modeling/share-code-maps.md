---
title: Exportovat a uložit map kódu
ms.date: 05/16/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 70c4cd238b6e5d31eced6a35ff0c7d24ab85a280
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63003130"
---
# <a name="share-code-maps"></a>Sdílení map kódu

Mapy kódu můžete uložit jako součást projektu sady Visual Studio, jako bitovou kopii nebo jako soubor ve formátu XPS.

## <a name="share-a-code-map-with-other-visual-studio-users"></a>Sdílet mapy kódu s ostatními uživateli aplikace Visual Studio

Použití **souboru** nabídky Uložit na mapě.

-nebo-

Chcete-li uložit mapy jako součást určitého projektu, na panelu nástrojů mapy, zvolte **sdílenou složku** > **přesunout \<CodeMapName > .dgml do**a pak zvolte projekt, kam chcete uložit Mapa.

![Přesunout do jiného projektu mapy](../modeling/media/codemapsmovemapmenu.png)

Visual Studio uloží mapy jako *.dgml* soubor, který můžete sdílet s ostatními uživateli aplikace Visual Studio Enterprise a Visual Studio Professional.

> [!NOTE]
> Než budete sdílet mapu s uživateli, kteří používají Visual Studio Professional, ujistěte se, že chcete-li rozbalit všechny skupiny, zobrazit skryté uzly a odkazy křížové skupiny a načíst všechny odstraněné uzly, které mají jiní uživatelé vidět na mapě. Jinak ostatní uživatelé nebudou moci tyto položky zobrazit.
>
> Při ukládání mapu, která je v projektu modelování nebo byl zkopírován z projektu modelování do jiného umístění, může dojít k následující chybě:
>
> "Nelze uložit *fileName* mimo adresář projektu. Propojené položky nejsou podporovány.“
>
> Aplikace Visual Studio zobrazí chybu, ale přesto vytvoří uloženou verzi. Aby se zabránilo chybě, vytvořte mapu mimo projekt modelování. Potom jej můžete uložit do požadovaného umístění. Nebude fungovat, pokud budete chtít soubor pouze zkopírovat do jiného umístění v řešení a potom jej uložit.

## <a name="export-a-code-map-as-an-image"></a>Exportovat jako obrázek mapy kódu

Při exportu mapu kódu jako bitovou kopii, můžete ji zkopírovat do jiných aplikací, jako je například Microsoft Word nebo PowerPoint.

1. Na panelu nástrojů Mapa kódu, zvolte **sdílenou složku** > **e-mailu jako obrázek** nebo **Kopírovat obrázek**.

2. Vložte obrázek do jiné aplikace.

## <a name="export-the-map-as-an-xps-file"></a>Mapování exportovat jako soubor ve formátu XPS

Pokud exportujete mapu kódu jako souboru XPS, zobrazí se v XML nebo XAML prohlížeče jako třeba Internet Explorer.

1. Na panelu nástrojů Mapa kódu, zvolte **sdílenou složku** > **e-mailu jako přenosný formát XPS** nebo **uložit jako přenosný formát XPS**.

2. Přejděte na požadované místo pro uložení souboru.

3. Název mapy kódu. Ujistěte se, že **uložit jako typ** pole nastavena na **soubory XPS (\*XPS)**. Zvolte **Uložit**.

## <a name="see-also"></a>Viz také:

- [Mapování závislostí pomocí map kódu](../modeling/map-dependencies-across-your-solutions.md)