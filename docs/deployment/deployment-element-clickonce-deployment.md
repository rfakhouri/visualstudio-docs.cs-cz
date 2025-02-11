---
title: '&lt;nasazení&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#subscription
- urn:schemas-microsoft-com:asm.v2#beforeApplicationStartup
- urn:schemas-microsoft-com:asm.v2#deploymentProvider
- urn:schemas-microsoft-com:asm.v2#update
- urn:schemas-microsoft-com:asm.v2#deployment
- urn:schemas-microsoft-com:asm.v2#expiration
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <deployment> element [ClickOnce deployment manifest]
ms.assetid: 4fafa9c2-97a0-4cea-b8fd-9746dca33af4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 90168dd760ba5619e2d50c864f54122b01ed66fa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62928933"
---
# <a name="ltdeploymentgt-element-clickonce-deployment"></a>&lt;nasazení&gt; – element (nasazení ClickOnce)
Určuje atributy použité pro nasazení aktualizací a vystavení systému.

## <a name="syntax"></a>Syntaxe

```xml

      <deployment
   install
   minimumRequiredVersion
   mapFileExtensions
   disallowUrlActivation
   trustUrlParameters
>
   <subscription>
         <update>
            <beforeApplicationStartup/>
            <expiration
               maximumAge
               unit
            />
         </update>
   </subscription>
   <deploymentProvider
      codebase
   />
</deployment>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `deployment` Element je povinný a je v `urn:schemas-microsoft-com:asm.v1` oboru názvů. Element má následující atributy.

| Atribut | Popis |
|--------------------------| - |
| `install` | Povinný parametr. Určuje, jestli tato aplikace definuje v Windows přítomnost **Start** nabídky a v Ovládacích panelech **přidat nebo odebrat programy** aplikace. Platné hodnoty jsou `true` a `false`. Pokud `false`, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nejnovější verze této aplikace se vždy spustí ze sítě a nerozpozná `subscription` elementu. |
| `minimumRequiredVersion` | Volitelné. Určuje minimální verzi této aplikace, které můžete spustit na straně klienta. Pokud číslo verze aplikace je menší než číslo verze v manifestu nasazení, aplikace se nespustí. Číslo verze musí být zadán ve formátu `N.N.N.N`, kde `N` je celé číslo bez znaménka. Pokud `install` atribut je `false`, `minimumRequiredVersion` nesmí být nastavený. |
| `mapFileExtensions` | Volitelné. Výchozí hodnota je `false`. Pokud `true`, všechny soubory v nasazení musí mít příponu .deploy. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Toto rozšíření z těchto souborů bude pruhu, poté, co je stáhne z webového serveru. Pokud publikujete aplikaci s použitím [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], automaticky přidá tuto příponu na všechny soubory. Tento parametr umožňuje všechny soubory v rámci [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení stahovat z webového serveru, která blokuje přenos souborů, které končí na "nebezpečného" rozšíření, jako je například .exe. |
| `disallowUrlActivation` | Volitelné. Výchozí hodnota je `false`. Pokud `true`, brání aplikace nainstalované ze spuštění klepnutím na adresu URL nebo zadáním adresy URL do aplikace Internet Explorer. Pokud `install` atribut není k dispozici, tento atribut se ignoruje. |
| `trustURLParameters` | Volitelné. Výchozí hodnota je `false`. Pokud `true`, umožňuje URL obsahuje parametry řetězce dotazu, které se předávají do aplikace, mnoho like příkazového řádku argumenty jsou předány do aplikace příkazového řádku. Další informace najdete v tématu [jak: Načtení informací řetězce dotazu do Online aplikace ClickOnce](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md).<br /><br /> Pokud `disallowUrlActivation` atribut je `true`, `trustUrlParameters` musí být vyloučeny z manifestu nebo explicitně nastavit na `false`. |

 `deployment` Element obsahuje také následující podřízené prvky.

## <a name="subscription"></a>předplatné
 Volitelné. Obsahuje `update` elementu. `subscription` Prvek nemá žádné atributy. Pokud `subscription` element neexistuje, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se nikdy vyhledat aktualizace. Pokud `install` atribut `deployment` element je `false`, `subscription` prvek je ignorován, protože [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci, která se spustí ze sítě, vždy používá nejnovější verzi.

## <a name="update"></a>update
 Povinný parametr. Tento element je podřízeným prvkem `subscription` elementu a obsahuje buď `beforeApplicationStartup` nebo `expiration` elementu. `beforeApplicationStartup` a `expiration` nelze zadat současně ve stejném manifestu nasazení.

 `update` Prvek nemá žádné atributy.

## <a name="beforeapplicationstartup"></a>beforeApplicationStartup
 Volitelné. Tento element je podřízeným prvkem `update` elementu a nemá žádné atributy. Když `beforeApplicationStartup` existuje element, aplikace bude blokována, pokud [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zjišťuje dostupnost aktualizací, pokud klient je online. Pokud tento prvek neexistuje, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nejprve vyhledá aktualizace na základě hodnot pro zadaný `expiration` elementu. `beforeApplicationStartup` a `expiration` nelze zadat současně ve stejném manifestu nasazení.

## <a name="expiration"></a>vypršení platnosti
 Volitelné. Tento element je podřízeným prvkem `update` elementu a nemá žádné podřízené položky. `beforeApplicationStartup` a `expiration` nelze zadat současně ve stejném manifestu nasazení. Pokud dojde k kontrolu aktualizací a je zjištěna aktualizovanou verzi, nová verze ukládá do mezipaměti průběhu stávající verzi. Nová verze se potom nainstaluje při příštím spuštění aplikace [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.

 `expiration` Element podporuje následující atributy.

|Atribut|Popis|
|---------------|-----------------|
|`maximumAge`|Povinný parametr. Určuje, kolik aktuální aktualizace by měla být předtím, než zkontroluje aktualizace aplikace. Jednotka času je určeno `unit` atribut.|
|`unit`|Povinný parametr. Jednotka času pro identifikuje `maximumAge`. Jsou platné jednotky `hours`, `days`, a `weeks`.|

## <a name="deploymentprovider"></a>deploymentProvider
 Pro rozhraní .NET Framework 2.0, tento element je povinný, pokud obsahuje manifest nasazení `subscription` oddílu. Pro rozhraní .NET Framework 3.5 a novější Tento element je volitelný a budou ve výchozím nastavení serveru a cestu souboru, ve kterém bylo zjištěno manifest nasazení.

 Tento element je podřízeným prvkem `deployment` elementu a nemá tento atribut.

| Atribut | Popis |
|------------| - |
| `codebase` | Povinný parametr. Určuje umístění, jako identifikátor URI (Uniform Resource), manifest nasazení, který se používá k aktualizaci [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Tento prvek umožňuje také předávání umístění aktualizace pro instalace z disku CD-ROM. Musí být platný identifikátor URI. |

## <a name="remarks"></a>Poznámky
 Můžete nakonfigurovat váš [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vyhledávání aktualizací po spuštění aplikace můžete spustit kontrolu aktualizací při spuštění, nebo nikdy nevyhledávat aktualizace. Můžete spustit kontrolu aktualizací při spuštění, ujistěte se, že `beforeApplicationStartup` existuje element v rámci `update` elementu. Kontrola aktualizací po spuštění, ujistěte se, že `expiration` existuje element v rámci `update` element a jsou k dispozici intervalů aktualizace.

 Chcete-li zakázat, vyhledávají se aktualizace, odeberte `subscription` elementu. Při zadávání v manifestu nasazení, aby nikdy vyhledat aktualizace, je můžete ručně zkontrolovat aktualizace pomocí <xref:System.Deployment.Application.ApplicationDeployment.CheckForUpdate%2A> metody.

 Další informace o jak deploymentProvider souvisí s aktualizací najdete v tématu [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).

## <a name="examples"></a>Příklady
 Následující příklad kódu ukazuje `deployment` prvek [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestu nasazení. V příkladu se používá `deploymentProvider` – element pro označení umístění upřednostňované aktualizace.

```xml
<deployment install="true" minimumRequiredVersion="2.0.0.0" mapFileExtension="true" trustUrlParameters="true">
    <subscription>
      <update>
        <expiration maximumAge="6" unit="hours" />
      </update>
    </subscription>
    <deploymentProvider codebase="http://www.adatum.com/MyApplication.application" />
  </deployment>
```

## <a name="see-also"></a>Viz také:
- [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)