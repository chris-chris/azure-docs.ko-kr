---
title: "Azure Data Catalog에서 데이터 자산 관리 | Microsoft Docs"
description: "문서는 Azure Data Catalog에 등록된 데이터 자산의 표시 여부 및 소유권을 제어하는 방법을 강조 표시합니다."
services: data-catalog
documentationcenter: 
author: steelanddata
manager: NA
editor: 
tags: 
ms.assetid: 623f5ed4-8da7-48f5-943a-448d0b7cba69
ms.service: data-catalog
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: data-catalog
ms.date: 01/18/2018
ms.author: maroche
ms.openlocfilehash: 5a4b2b5734bf8bfbbc45a65b02362d1fa37b1a87
ms.sourcegitcommit: be9a42d7b321304d9a33786ed8e2b9b972a5977e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="manage-data-assets-in-azure-data-catalog"></a>Azure Data Catalog에서 데이터 자산 관리
## <a name="introduction"></a>소개
Azure Data Catalog는 사용자가 분석을 수행하고 결정을 내리는 데 필요한 데이터 원본을 쉽게 검색하고 이해할 수 있도록 데이터 원본 검색을 위해 설계되었습니다. 이러한 검색 기능은 모든 사용자가 가장 넓은 범위의 사용 가능한 데이터 원본을 이해하고 찾을 수 있는 경우 엄청난 영향을 가집니다. 이러한 요소를 고려하여 데이터 카탈로그의 기본 동작은 모든 등록된 데이터 원본을 모든 카탈로그 사용자에게 표시하며 검색할 수 있게 합니다.

데이터 카탈로그는 사용자가 데이터 자체에 액세스할 권한을 주지 않습니다. 데이터 원본의 소유자가 데이터 액세스를 제어합니다. 데이터 카탈로그를 사용하면 데이터 원본을 검색하고 카탈로그에 등록된 원본과 관련된 메타데이터를 볼 수 있습니다.

그러나 데이터 원본을 특정 사용자 또는 특정 그룹의 구성원에게만 표시해야 할 상황이 있을 수 있습니다. 이러한 시나리오에서 사용자는 카탈로그 내에서 등록된 데이터 자산의 소유권을 가져온 다음 소유한 자산의 표시 여부를 제어할 수 있습니다.

> [!NOTE]
> 이 문서에서 설명한 기능은 Azure Data Catalog의 표준 버전에서만 사용할 수 있습니다. 무료 버전에서는 소유권 및 데이터 자산의 표시를 제한하기 위한 기능을 제공하지 않습니다.
>
>

## <a name="manage-ownership-of-data-assets"></a>데이터 자산의 소유권 관리
기본적으로 데이터 카탈로그에 등록된 데이터 자산은 소유되지 않습니다. 카탈로그에 액세스할 수 있는 권한을 가진 모든 사용자는 이러한 자산을 검색하고 주석을 달 수 있습니다. 사용자는 소유하지 않은 데이터 자산의 소유권을 가져올 수 있고 자신이 소유한 자산의 표시를 제한할 수 있습니다.

데이터 카탈로그의 데이터 자산을 소유하는 경우 소유자에게 권한을 부여받은 사용자만이 자산을 검색하고 해당 메타데이터를 볼 수 있으며 소유자만이 카탈로그에서 자산을 삭제할 수 있습니다.

> [!NOTE]
> 데이터 카탈로그의 소유권은 카탈로그에 저장된 메타데이터에 영향을 줍니다. 소유권은 기본 데이터 원본에 대한 권한을 부여하지 않습니다.
>
>

### <a name="take-ownership"></a>소유권 가져오기
사용자는 데이터 카탈로그 포털에서 **소유권 가져오기** 옵션을 선택하여 데이터 자산의 소유권을 가져올 수 있습니다. 소유되지 않은 데이터 자산의 소유권을 가져오는 데 특별한 권한이 필요하지 않습니다. 모든 사용자는 소유되지 않은 데이터 자산을 소유할 수 있습니다.

### <a name="add-owners-and-co-owners"></a>소유자 및 공동 소유자 추가
데이터 자산이 이미 소유된 경우 다른 사용자는 소유권을 가질 수 없습니다. 기존 소유자에 의해 공동 소유자로 추가되어야 합니다. 소유자는 추가 사용자 또는 보안 그룹을 공동 소유자로 추가할 수 있습니다.

> [!NOTE]
> 소유한 데이터 자산에 둘 이상의 개인이 소유자인 것이 좋습니다.
>
>

### <a name="remove-owners"></a>소유자 제거
자산 소유자가 공동 소유자를 추가할 수 있는 것처럼 자산 소유자는 공동 소유자를 제거할 수 있습니다.

자신을 소유자에서 제거하는 자산 소유자는 자산을 더 이상 관리할 수 없습니다. 자산 소유자가 자신을 소유자에서 제거하고 다른 공동 소유자가 없는 경우 자산은 소유하지 않은 상태로 변환됩니다.

## <a name="control-visibility"></a>컨트롤 표시 여부
데이터 자산 소유자는 자신이 소유한 데이터 자산의 표시 여부를 제어할 수 있습니다. 모든 데이터 카탈로그 사용자가 데이터 자산을 검색하고 볼 수 있는 기본값에서 표시를 제한하려면 자산 소유자는 자산에 대한 속성에서 표시 여부 설정을 **모두**에서 **소유자 및 다음 사용자**로 설정/해제할 수 있습니다. 그런 다음 소유자는 특정 사용자 및 보안 그룹을 추가할 수 있습니다.

> [!NOTE]
> 가능한 경우에는 개별 사용자가 아닌 보안 그룹에 자산 소유권 및 표시 여부 권한을 할당해야 합니다.
>
>

## <a name="catalog-administrators"></a>카탈로그 관리자
데이터 카탈로그 관리자는 암시적으로 카탈로그에서 모든 자산의 공동 소유자입니다. 자산 소유자는 관리자에게 표시되지 않도록 할 수 없고 관리자는 카탈로그의 모든 데이터 자산의 소유권 및 표시 여부를 관리할 수 있습니다.

## <a name="summary"></a>요약
메타데이터 및 데이터 자산 검색에 대한 데이터 카탈로그의 크라우드소싱 모델을 사용하면 모든 카탈로그 사용자가 기여하고 검색할 수 있습니다. 데이터 카탈로그의 표준 버전은 특정 데이터 자산의 표시 및 사용을 제한하는 소유권 및 관리를 위해 설계되었습니다.
