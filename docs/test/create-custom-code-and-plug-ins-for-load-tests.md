---
title: Vytvoření vlastního kódu a modulů plugin pro zátěžové testování
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.dialog.recorderplugin
helpviewer_keywords:
- Web performance tests, plug-ins
- load tests, plug-ins
ms.assetid: 0c0fcc99-673b-4ea0-a268-0475f66e5cb6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8382d5014b88d9f1711a082e46530e1e3dfb96e4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62965450"
---
# <a name="create-custom-code-and-plug-ins-for-load-tests"></a>Vytvoření vlastního kódu a modulů plugin pro zátěžové testování

Vlastní modul plug-in používá kód, který lze vytvořit a připojit k zátěžovému testu nebo testu výkonnosti webu. Rozhraní API zátěžového testu a API výkonnostních testů webu můžete použít k vytvoření vlastních modulů plug-in pro rozšíření integrovaných funkcí. Můžete přidat více modulů plug-in do zátěžového testu.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-|-----------------------|
|**Vytvořit vlastní modul plug-in pro zátěžový test**: Můžete vytvořit vlastní modul plug-in pro přidání další funkce testování k zátěžovému testu můžete použít rozhraní API zátěžového testu.|-   [Jak: Použití rozhraní API zátěžového testu](../test/how-to-use-the-load-test-api.md)<br />-   [Jak: Vytvoření modulu Plugin pro zátěžový test](../test/how-to-create-a-load-test-plug-in.md)|
|**Vytvořte vlastní modul plug-in pro test výkonnosti webu:** Můžete vytvořit vlastní modul plug-in pro přidání další funkce testování do testu výkonnosti webu, včetně webu můžete použít API výkonnostních testů webu. Můžete také vytvořit testu webové služby.<br /><br /> Kromě toho můžete vytvořit webového modulu plug-in rekordéru, který můžete upravit test výkonnosti webu poté, co je zaznamenán, ale předtím, než se zobrazí v prohlížeči výsledků testů webového výkonu.|-   [Jak: Použít API výkonnostních testů webu](../test/how-to-use-the-web-performance-test-api.md)<br />-   [Jak: Vytvoření modulu Plugin pro test výkonnosti webu](../test/how-to-create-a-web-performance-test-plug-in.md)<br />-   [Jak: Vytvoření modulu Plugin úrovni požadavků](../test/how-to-create-a-request-level-plug-in.md)<br />-   [Jak: Vytvoření testu webové služby](../test/how-to-create-a-web-service-test.md)<br />-   [Jak: Vytvoření modulu Plugin rekordéru](../test/how-to-create-a-recorder-plug-in.md)|
|**Přidání funkcí uživatelského rozhraní do prohlížeče výsledků testu výkonu webu:** Další funkce uživatelského rozhraní můžete přiřadit pomocí doplňku sady Visual Studio prohlížeče výsledků testu webového výkonu.|-   [Jak: Vytvořit doplněk sady Visual Studio pro prohlížeč výsledků testu výkonnosti webu](../test/how-to-create-an-add-in-for-the-web-performance-test-results-viewer.md)|
|**Vytvoření vlastního protokolu HTTP editoru těla:** Můžete vytvořit vlastní editor pro úpravu binárních nebo řetězcových odpovědí ve formátu XML z webové služby.|-   [Jak: Vytvořit vlastní těla protokolu HTTP editor pro editor testu výkonnosti webu](../test/how-to-create-a-custom-http-body-editor-for-the-web-performance-test-editor.md)|

## <a name="reference"></a>Odkaz

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting>

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Generování a spuštění programový test výkonnosti webu](../test/generate-and-run-a-coded-web-performance-test.md)