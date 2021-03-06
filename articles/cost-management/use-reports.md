---
title: Azure Cost Management에서 비용 관리 보고서 사용 | Microsoft Docs
description: 이 문서에서는 Cloudyn 포털에서 다양한 비용 관리 보고서를 사용하는 방법을 설명합니다.
services: cost-management
keywords: ''
author: bandersmsft
ms.author: banders
ms.date: 04/26/2018
ms.topic: conceptual
ms.service: cost-management
manager: dougeby
ms.custom: ''
ms.openlocfilehash: db7663623ada5d7799c46018be9e3b66afd004ca
ms.sourcegitcommit: e2adef58c03b0a780173df2d988907b5cb809c82
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="use-cost-management-reports"></a>비용 관리 보고서 사용

이 문서에서는 Cloudyn 포털에서 다양한 비용 관리 보고서를 사용하는 방법을 설명합니다. 대부분의 Cloudyn 보고서는 직관적이며 모양과 느낌이 일관됩니다. Cloudyn 보고서에 관한 개요는 [비용 보고서 이해](understanding-cost-reports.md)를 참조하세요. 또한 이 문서에서는 대부분의 보고서에 사용되는 여러 옵션 및 필드도 설명합니다.

## <a name="cost-analysis-reports"></a>비용 분석 보고서

비용 분석 보고서는 클라우드 공급자의 청구 데이터를 표시합니다. 보고서를 사용하여 청구 파일에 항목별로 작성된 여러 데이터 세그먼트를 그룹화하고 세부적으로 들여다볼 수 있습니다. 보고서를 사용하여 클라우드 공급자의 원시 청구 데이터에 대한 세부적인 비용을 탐색할 수 있습니다.

비용 분석 보고서는 비용을 태그별로 그룹화하지 않습니다. 태그 기반 보고는 Cost Allocation 360을 사용하여 비용 모델을 만든 후 비용 할당 보고서 세트에서만 사용할 수 있습니다.

### <a name="actual-cost-analysis"></a>실제 비용 분석

실제 비용 분석 보고서는 지속적인 비용 및 1 회 요금을 포함하여 주 비용 기여요인을 보여 줍니다.

 실제 비용 분석 보고서를 사용하여 다음을 수행합니다.

- 지정된 시간 프레임 동안 소비한 실제 비용을 분석 및 모니터링
- 임계값 경고 예약
- 쇼백 및 차지백 비용 분석

#### <a name="to-use-the-actual-cost-analysis-report"></a>실제 비용 분석 보고서를 사용하려면

적어도 다음 단계를 수행합니다. 또한 다른 옵션 및 필드를 사용할 수도 있습니다.

1. 날짜 범위를 선택합니다.
2. 필터를 선택합니다.

보고서 결과를 마우스 오른쪽 버튼으로 클릭하여 세부적으로 들여다보고 더 자세한 정보를 볼 수 있습니다.

![실제 비용 분석 보고서 예제](./media/use-reports/actual-cost-analysis.png)

### <a name="actual-cost-over-time"></a>시간에 따른 실제 비용

시간에 따른 실제 비용 보고서는 정의된 시간 확인에 대해 비용을 분배하는 표준 비용 분석 보고서입니다. 이 보고서는 추세를 관찰하고 지출 이상값을 탐지할 수 있도록 시간에 대한 지출을 표시합니다. 이 보고서는 선택한 시간 프레임 동안 소비한 지속적 비용 및 1회 예약 인스턴스 요금을 포함하여 주 비용 기여요인을 보여 줍니다.

시간에 따른 실제 비용 보고서를 사용하여 다음을 수행합니다.

- 시간에 따른 비용 추세를 참조하세요.
- 비용에서 이상값을 찾습니다.
- Amazon Web Services와 관련된 모든 비용 관련 질문을 찾습니다.

#### <a name="to-use-the-actual-cost-over-time-report"></a>시간에 따른 실제 비용 보고서를 사용하려면:

적어도 다음 단계를 수행합니다. 또한 다른 옵션 및 필드를 사용할 수도 있습니다.

- 날짜 범위를 선택합니다.

예를 들어 그룹을 선택하여 시간에 따른 비용을 볼 수 있습니다. 그런 다음 결과 범위를 좁히려면 필터를 추가합니다.

![시간에 따른 실제 비용 보고서 예제](./media/use-reports/actual-cost-over-time.png)



### <a name="amortized-cost-reports"></a>사용한 비용 보고서

이 사용한 비용 보고서 세트는 선형화된 비사용량 기반 서비스 요금 또는 1회 지급 비용을 보여 주며 비용을 수명 주기 전체에 걸쳐 균등하게 분산합니다.

예를 들어 1회 요금은 다음을 포함할 수 있습니다.

- 연간 지원 요금
- 연간 보안 구성 요소 요금
- 예약 인스턴스 구입 요금
- 일부 Azure Marketplace 항목

청구 파일에서 1회 요금은 서비스 사용 시작 및 종료 날짜 또는 타임스탬프가 동일한 값을 가진다는 특징이 있습니다. 이때 Cloudyn은 이들을 사용할 수 있는 1회 요금으로 인식합니다. 주문형 사용량 비용을 이용하는 다른 사용량 기반 서비스는 사용할 수 없습니다.

사용한 비용을 보여 주려면 시간에 따른 실제 비용 보고서의 다음 예제 이미지를 검토합니다. 이 예제에서는 8월 23일의 비용이 급증했음을 보여 줍니다. 일상적인 일별 비용 추세에 비해 이상이 있어 보입니다. 근본 원인 분석 및 데이터 탐색에서는 이 비용을 1회 요금으로 구입하였고 해당일에 청구된 연간 AWS 서비스 APN 예약으로 식별했습니다. 다음 섹션에서 이 비용을 사용하는 방법을 확인할 수 있습니다.

![1회 비용을 보여 주는 시간에 따른 실제 비용 보고서 예제](./media/use-reports/actual-amort-example.png)

#### <a name="to-use-the-amortized-cost-over-time-report"></a>시간에 따른 사용 비용 보고서를 사용하려면:

적어도 다음 단계를 수행합니다. 또한 다른 옵션 및 필드를 사용할 수도 있습니다.

1. 날짜 범위를 선택합니다.
2. 서비스 및 공급자를 선택합니다.

앞의 예를 이어서 보면 다음 이미지에서 이제 1회 비용이 사용되었음을 확인할 수 있습니다.

![시간에 따른 사용 비용 보고서 예제](./media/use-reports/amort-cost-over-time.png)

앞의 이미지는 시간에 따른 APN 예약 비용에 대해 사용한 비용을 보여 줍니다. 이 보고서는 1회 요금 사용 및 APN 비용을 연간 예약 구입으로 보여 줍니다. APN 비용은 일일 기준으로 예약 선행 비용의 1/365로 균일하게 분산됩니다.

## <a name="cost-allocation-analysis-reports"></a>비용 할당 분석 보고서

비용 할당 분석 보고서는 Cost Allocation 360을 사용하여 비용 모델을 만든 후 사용할 수 있습니다. Cloudyn은 비용/청구 데이터를 처리하고 데이터를 클라우드 계정의 사용량 및 태그 데이터와 대조합니다. 데이터를 대조하려면 Cloudyn이 사용량 데이터에 액세스해야 합니다. 자격 증명이 없는 계정은 분류되지 않은 리소스로 레이블이 지정됩니다.

### <a name="cost-analysis-report"></a>비용 분석 보고서

비용 분석 보고서는 선택된 시간 프레임 동안 클라우드 소비 및 지출에 대한 통찰력을 제공합니다. Cost Allocation Manager에서 설정한 정책은 비용 분석 보고서에 사용됩니다.

Cloudyn은 이 보고서를 어떻게 계산합니까?

Cloudyn은 계정 선호도를 적용하여 할당이 각 연결된 계정의 무결성을 유지하도록 합니다. 선호도는 특정 서비스를 사용하지 않는 계정이 이 서비스의 비용을 해당 계정에 할당하지 않도록 합니다. 해당 계정에서 발생한 비용은 해당 계정에 남아 있으며 할당 정책에 의해 계산되지 않습니다. 예를 들어 연결된 계정 다섯 개가 있다고 가정할 때, 이들 중 셋만이 저장소 서비스를 사용한다면 저장소 서비스의 비용은 세 계정의 태그에 대해서만 할당됩니다.

 비용 분석 보고서를 사용하여 다음을 수행합니다.

- 특정 시간 프레임에 대해 전체 배포의 집계된 보기를 표시합니다.
- 비용 모델에서 만든 정책을 기반으로 태그 범주별로 비용을 봅니다.

#### <a name="to-use-the-cost-analysis-report"></a>비용 분석 보고서를 사용하려면:

1. 날짜 범위를 선택합니다.
2. 필요한 경우 태그를 추가합니다.
3. 그룹을 추가합니다.
4. 이전에 만든 비용 모델을 선택합니다.

다음 이미지는 예제 비용 분석 보고서를 선버스트(sunburst) 형식으로 보여 줍니다. 링은 그룹을 표시합니다. 외부 원은 서비스를 나타내며 내부 원은 단위를 나타냅니다.

![비용 분석 보고서 예제](./media/use-reports/cost-analysis01.png)



다음은 같은 정보를 테이블 보기로 본 예입니다.

![비용 분석 보고서 예제](./media/use-reports/cost-analysis02.png)



### <a name="cost-over-time-report"></a>시간에 따른 비용 보고서

시간에 따른 비용 보고서는 추세를 관찰하고 배포의 이상값을 탐지할 수 있도록 시간에 따른 지출을 표시합니다. 이는 기본적으로 정의된 기간에 대해 분배된 비용을 보여 줍니다. 이 보고서는 선택한 시간 프레임 동안 소비한 지속적 비용 및 1회 예약 인스턴스 요금을 포함하여 주 비용 기여요인을 포함합니다. Cost Manager 360에서 설정한 정책을 이 보고서에 사용할 수 있습니다.

시간에 따른 비용 보고서를 사용하여 다음을 수행합니다.

- 시간에 따른 변화 및 날짜(또는 날짜 범위)에 따라 변하는 영향을 확인합니다.
- 특정 인스턴스에 대해 시간에 따른 비용을 분석합니다.
- 특정 인스턴스에 대해 비용이 증가한 이유를 이해합니다.

#### <a name="to-use-the-cost-over-time-report"></a>시간에 따른 비용 보고서를 사용하려면:

1. 날짜 범위를 선택합니다.
2. 필요한 경우 태그를 추가합니다.
3. 그룹을 추가합니다.
4. 이전에 만든 비용 모델을 선택합니다.
5. 실제 비용 또는 사용한 비용을 선택합니다.
6. 할당 규칙을 적용하여 원시 청구 데이터 보기를 보는지 아니면 다시 계산된 비용 보기를 보는지 선택합니다.

다음은 보고서의 예입니다.

![시간에 따른 비용 예제](./media/use-reports/cost-over-time.png)



## <a name="next-steps"></a>다음 단계

- Cost Management에 대한 첫 번째 자습서를 아직 완료하지 않은 경우 [사용량 및 비용 검토](tutorial-review-usage.md)에서 읽어 보십시오.
