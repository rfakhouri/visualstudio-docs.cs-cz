---
title: '&lt;appAddin&gt; – element (vývoj pro Office v sadě Visual Studio)'
titleSuffix: ''
ms.date: 02/02/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <appAddin> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b53fcfaa28694b88f3401d0e2e40b157ba7c3201
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54875989"
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;appAddin&gt; – element (vývoj pro Office v sadě Visual Studio)
  **AppAddin** elementu `vstov4` obor názvů ukládá informace specifické pro přizpůsobení pro doplňky VSTO.

## <a name="syntax"></a>Syntaxe

```xml
<appAddin
  application
  loadBehavior
  keyName>
  <friendlyName>
  <description>
  <formRegions></formRegions>
</appAddin>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 **AppAddin** element je povinný a je v `vstov4` oboru názvů. Existuje pouze jeden **appAddin** element definovaný v manifestu aplikace.

 **AppAddin** element má následující atributy.

|Atribut|Popis|
|---------------|-----------------|
|**Aplikace**|Povinný parametr. Identifikuje aplikaci Microsoft Office. Hodnota může být jeden z následujících akcí: Aplikace Excel, InfoPath, Outlook, PowerPoint, projekt, Visia nebo Word.|
|**loadBehavior**|Volitelné. Ve výchozím nastavení **loadBehavior** se povoluje nastavením této hodnoty. Pro ladění doplňku VSTO lze zakázat nastavením této hodnoty na dva. Další informace najdete v tabulce s názvem hodnotách LoadBehavior v [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).|
|**keyName**|Povinný parametr. Tato hodnota je název klíče registru, který se použije k načtení doplňku VSTO aplikací. Další informace najdete v tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).|

 **AppAddin** element má následující podřízené prvky.

### <a name="friendlyname"></a>friendlyName
 Volitelné. **FriendlyName** element je podrobně [ &#60;friendlyName&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md).

### <a name="description"></a>description
 Volitelné. **Popis** element je podrobně [ &#60;popis&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/description-element-office-development-in-visual-studio.md).

### <a name="formregions"></a>formregions –
 Vyžaduje se jenom pro aplikaci Outlook doplňků VSTO, které zahrnují oblasti formuláře. **FormRegions** element je podrobně [ &#60;formRegions&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/formregions-element-office-development-in-visual-studio.md).

## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje **appAddin** prvky v aplikaci Outlook řešení nasazeným v rámci [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstov4:appAddIn
  application="Outlook"
  loadBehavior="3"
  keyName="ContosoOutlookAddIn">
  <vstov4:friendlyName>
    ContosoOutlookAddIn
  </vstov4:friendlyName>
  <vstov4:description>
    ContosoOutlookAddIn - Outlook VSTO Add-in
    created with Visual Studio Tools for Office
  </vstov4:description>
  <vstov4:formRegions>
    <vstov4:formRegion
        name="OutlookAddIn1.FormRegion1">
      <vstov4:messageClass name="IPM.Note" />
      <vstov4:messageClass name="IPM.Contact" />
      <vstov4:messageClass name="IPM.Appointment" />
    </vstov4:formRegion>
  </vstov4:formRegions>
</vstov4:appAddIn>
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)