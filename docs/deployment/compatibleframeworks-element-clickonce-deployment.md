---
title: '&lt;compatibleFrameworks&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 99db3d51414197df469aaa2eabe97e0967c31b05
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66746032"
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt; – element (nasazení ClickOnce)
Určuje verzi rozhraní .NET Framework, ve kterém můžete tuto aplikaci nainstalovat a spustit.

> [!NOTE]
> [*MageUI.exe* ](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client) nepodporuje `compatibleFrameworks` element při ukládání manifestu aplikace, který již byl podepsán pomocí certifikátu [ *MageUI.exe*](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client). Místo toho je nutné použít [ *Mage.exe*](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).

## <a name="syntax"></a>Syntaxe

```xml
<compatibleFrameworks
      SupportUrl> 
   <framework
      targetVersion
      profile
      supportedRuntime
   /> 
</ compatibleFrameworks>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `compatibleFrameworks` Element se vyžaduje pro manifesty nasazení, které se zaměřují [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] runtime k dispozici v rozhraní .NET Framework 4 nebo novější. `compatibleFrameworks` Element obsahuje jeden nebo více `framework` elementy, které určují verze rozhraní .NET Framework, na kterých tato aplikace mohla spustit. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Modul runtime spustí aplikaci v prvním dostupné `framework` v tomto seznamu.

 V následující tabulce jsou uvedeny atribut, který `compatibleFrameworks` elementu podporuje.

|Atribut|Popis|
|---------------|-----------------|
|`S``upportUrl`|Volitelné. Určuje adresu URL, kde lze stáhnout upřednostňované kompatibilní verze rozhraní .NET Framework.|

## <a name="framework"></a>rozhraní
 Povinný parametr. V následující tabulce jsou uvedeny atributy, které `framework` elementu podporuje.

|Atribut|Popis|
|---------------|-----------------|
|`targetVersion`|Povinný parametr. Určuje číslo verze cílového rozhraní .NET Framework.|
|`profile`|Povinný parametr. Určuje profil cílového rozhraní .NET Framework.|
|`supportedRuntime`|Povinný parametr. Určuje číslo verze modulu runtime přidružený k cílové rozhraní .NET Framework.|

## <a name="remarks"></a>Poznámky

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje `compatibleFrameworks` prvek [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestu nasazení. Toto nasazení můžete spustit na [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]. Lze je také spustit v rozhraní .NET Framework 4 vzhledem k tomu, že je nadstavbou jazyka [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)].

```xml
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">
  <framework
      targetVersion="4.0"
      profile="Client"
      supportedRuntime="4.0.30319" />
</compatibleFrameworks>
```

## <a name="see-also"></a>Viz také:
- [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)