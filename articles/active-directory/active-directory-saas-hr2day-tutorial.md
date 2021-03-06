---
title: '자습서: HR2day by Merces와 Azure Active Directory 통합 | Microsoft Docs'
description: Azure Active Directory와 HR2day by Merces 간에 Single Sign-On을 구성하는 방법에 대해 알아봅니다.
services: active-directory
documentationCenter: na
author: jeevansd
manager: mtillman
ms.assetid: 853d08c9-27b1-48d4-b8e7-3705140eb67f
ms.service: active-directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 06/24/2017
ms.author: jeedes
ms.openlocfilehash: 6b6f839ace5d80d41b242992feba8dea546b51c2
ms.sourcegitcommit: b6319f1a87d9316122f96769aab0d92b46a6879a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2018
ms.locfileid: "34340875"
---
# <a name="tutorial-azure-active-directory-integration-with-hr2day-by-merces"></a>자습서: HR2day by Merces와 Azure Active Directory 통합

이 자습서에서는 Azure AD(Azure Active Directory)와 HR2day by Merces를 통합하는 방법에 대해 알아봅니다.

HR2day by Merces를 Azure AD와 통합하면 다음과 같은 이점이 제공됩니다.

- HR2day by Merces에 대한 액세스 권한이 있는 사용자를 Azure AD에서 제어할 수 있습니다.
- 사용자가 해당 Azure AD 계정으로 HR2day by Merces에 자동으로 로그인되도록 설정할 수 있습니다.
- 단일 중앙 위치인 Azure Portal에서 계정을 관리할 수 있습니다.

Azure AD와 SaaS 앱 통합에 대한 자세한 내용은 [Azure Active Directory를 사용한 응용 프로그램 액세스 및 Single Sign-On이란 무엇인가요?](manage-apps/what-is-single-sign-on.md)를 참조하세요.

## <a name="prerequisites"></a>필수 조건

HR2day by Merces와의 Azure AD 통합을 구성하려면 다음 항목이 필요합니다.

- Azure AD 구독
- HR2day by Merces Single Sign-On이 설정된 구독

> [!NOTE]
> 이 자습서의 단계를 테스트하기 위해 프로덕션 환경을 사용하는 것은 바람직하지 않습니다.

이 자습서의 단계를 테스트하려면 다음 권장 사항을 따릅니다.

- 꼭 필요한 경우가 아니면 프로덕션 환경을 사용하지 마세요.
- 아직 없는 경우 [Azure AD의 1개월 평가판](https://azure.microsoft.com/pricing/free-trial/)을 사용합니다.  

## <a name="scenario-description"></a>시나리오 설명
이 자습서에서는 테스트 환경에서 Azure AD Single Sign-On을 테스트 합니다. 여기에서 설명된 시나리오는 다음 두 가지 주요 구성 요소로 이루어져 있습니다.

1. 갤러리에서 HR2day by Merces 추가
2. Azure AD Single Sign-on 구성 및 테스트

## <a name="add-hr2day-by-merces-from-the-gallery"></a>갤러리에서 HR2day by Merces 추가
HR2day by Merces와의 Azure AD 통합을 구성하려면 갤러리의 HR2day by Merces를 관리되는 SaaS 앱 목록에 추가합니다.

**갤러리에서 HR2day by Merces를 추가하려면 다음 단계를 수행합니다.**

1. [Azure Portal](https://portal.azure.com)의 왼쪽 탐색 창에서 **Azure Active Directory** 아이콘을 선택합니다. 

    ![Active Directory][1]

2. **엔터프라이즈 응용 프로그램**으로 이동합니다. 그런 후 **모든 응용 프로그램**으로 이동합니다.

    ![응용 프로그램][2]
    
3. 새 응용 프로그램을 추가하려면 대화 상자 맨 위 있는 **새 응용 프로그램** 단추를 선택합니다.

    ![응용 프로그램][3]

4. 검색 상자에 **HR2day by Merces**를 입력합니다.

    ![Azure AD 테스트 사용자 만들기](./media/active-directory-saas-hr2day-tutorial/tutorial_hr2daybymerces_search.png)

5. 결과 패널에서 **HR2day by Merces**를 선택하고 **추가** 단추를 선택하여 응용 프로그램을 추가합니다.

    ![Azure AD 테스트 사용자 만들기](./media/active-directory-saas-hr2day-tutorial/tutorial_hr2daybymerces_addfromgallery.png)

##  <a name="configure-and-test-azure-ad-single-sign-on"></a>Azure AD Single Sign-On 구성 및 테스트
이 섹션에서는 “Britta Simon”이라는 테스트 사용자를 기반으로 HR2day by Merces에서 Azure AD Single Sign-On을 구성하고 테스트합니다.

Single Sign-On이 작동하려면 Azure AD에서 Azure AD 사용자에 해당하는 HR2day by Merces 사용자가 누구인지 알고 있어야 합니다. 즉, Azure AD 사용자와 HR2day by Merces의 관련 사용자 간에 연결이 형성되어야 합니다.

HR2day by Merces에서 Azure AD의 **사용자 이름**을 **Username**으로 할당하여 관계를 설정합니다.

HR2day by Merces에서 Azure AD Single Sign-On을 구성하고 테스트하려면 다음 구성 요소를 완료해야 합니다.

1. [Azure AD Single Sign-On 구성](#configuring-azure-ad-single-sign-on): 사용자가 이 기능을 사용할 수 있도록 합니다.
2. [Azure AD 테스트 사용자 만들기](#creating-an-azure-ad-test-user): Britta Simon으로 Azure AD Single Sign-On을 테스트합니다.
3. [HR2day by Merces 테스트 사용자 만들기](#creating-an-hr2day-by-merces-test-user): Britta Simon의 Azure AD 표현과 연결되는 대응 사용자를 HR2day by Merces에 만듭니다.
4. [Azure AD 테스트 사용자 할당](#assigning-the-azure-ad-test-user): Britta Simon이 Azure AD Single Sign-on을 사용할 수 있도록 합니다.
5. [Single Sign-on 테스트](#testing-single-sign-on): 구성이 작동하는지 여부를 확인합니다.

### <a name="configure-azure-ad-single-sign-on"></a>Azure AD Single Sign-On 구성

이 섹션에서는 Azure Portal에서 Azure AD Single Sign-On을 사용하도록 설정하고 HR2day by Merces 응용 프로그램에서 Single Sign-On을 구성합니다.

**HR2day by Merces에서 Azure AD Single Sign-On을 구성하려면 다음 단계를 수행합니다.**

1. Azure Portal의 **HR2day by Merces** 응용 프로그램 통합 페이지에서 **Single Sign-On**을 선택합니다.

    ![Single Sign-on 구성][4]

2. Single Sign-On을 사용하도록 설정하려면 **Single Sign-On** 대화 상자에서 **모드**를 **SAML 기반 로그온**으로 선택합니다.
 
    ![Single Sign-On 구성](./media/active-directory-saas-hr2day-tutorial/tutorial_hr2daybymerces_samlbase.png)

3. **HR2day by Merces 도메인 및 URL** 섹션에서 다음 단계를 수행합니다.

    ![Single Sign-On 구성](./media/active-directory-saas-hr2day-tutorial/tutorial_hr2daybymerces_url.png)

    a. **로그온 URL** 텍스트 상자에서 다음과 같은 패턴을 사용하여 URL을 입력합니다. `https://<tenantname>.force.com/<instancename>`

    나. **식별자** 텍스트 상자에서 다음과 같은 패턴을 사용하여 URL을 입력합니다. `https://hr2day.force.com/<companyname>`

    > [!NOTE] 
    > 이러한 값은 실제 값이 아닙니다. 실제 로그온 URL 및 식별자로 값을 업데이트합니다. 이러한 값을 얻으려면 [HR2day by Merces 클라이언트 지원 팀](mailto:servicedesk@merces.nl)에 문의하세요. 
 


4. **SAML 서명 인증서** 섹션에서 **인증서(Base64)** 를 선택한 후 컴퓨터에 인증서 파일을 저장합니다.

    ![Single Sign-On 구성](./media/active-directory-saas-hr2day-tutorial/tutorial_hr2daybymerces_certificate.png) 

5. 이 섹션에서는 사용자가 Azure AD의 계정으로 HR2day by Merces에 인증할 수 있게 하는 방법을 설명합니다. SAML 프로토콜을 기반으로 하는 페더레이션을 사용하여 이를 수행합니다.

    HR2day by Merces 응용 프로그램은 특정 서식에서 SAML 어설션을 예상하며 이는 SAML 토큰에 사용자 지정 특성 매핑을 추가합니다. 다음 스크린샷은 이에 대한 예제를 보여 줍니다. 

    ![Single Sign-On 구성](./media/active-directory-saas-hr2day-tutorial/tutorial_hr2day_00.png)
    
    > [!NOTE] 
    SAML 어설션을 구성하기 전에 [HR2day by Merces 클라이언트 지원 팀](mailto:servicedesk@merces.nl)에 문의하여 테넌트에 대한 고유 식별자 특성 값을 요청하세요. 다음 섹션의 단계를 완료하려면 이 값이 필요합니다. 

6. **Single Sign-On** 대화 상자의 **사용자 특성** 섹션에서 다음 이미지에 표시된 것과 같이 SAML 토큰 특성을 구성합니다. 다음 단계를 수행합니다.
    
      | 특성 이름    |   특성 값 |  
    | ------------------- | -------------------- |    
    | ATTR_LOGINCLAIM | join([mail],"102938475Z","@" |
    
      a. **특성 추가** 대화 상자를 열려면 **특성 추가**를 선택합니다.

    ![Single Sign-On 구성](./media/active-directory-saas-hr2day-tutorial/tutorial_attribute_04.png)

    ![Single Sign-on 구성](./media/active-directory-saas-hr2day-tutorial/tutorial_attribute_05.png)

    나. **이름** 상자에 **ATTR_LOGINCLAIM**을 입력합니다.

    다. **값** 목록에서 **Join()** 을 선택합니다.

    d. **String1** 목록에서 **user.mail**을 선택합니다.

    e. **String2**의 경우 HR2day 팀에서 제공하는 고유 식별자를 입력합니다.

    f. **구분 기호** 상자에 **@** 을 입력합니다.
    
    g. **확인**을 선택합니다.

7. **저장** 단추를 선택합니다.

    ![Single Sign-On 구성](./media/active-directory-saas-hr2day-tutorial/tutorial_general_400.png)

8. **HR2day by Merces 구성** 섹션에서 **HR2day by Merces 구성**을 선택하여 **로그온 구성** 창을 엽니다. **빠른 참조** 섹션에서 **로그아웃 URL**, **SAML 엔터티 ID** 및 **SAML Single Sign-On 서비스 URL**을 복사합니다.

    ![Single Sign-On 구성](./media/active-directory-saas-hr2day-tutorial/tutorial_hr2daybymerces_configure.png) 

9. 응용 프로그램에 대한 SSO를 구성하려면 [HR2day by Merces 클라이언트 지원 팀](mailTo:servicedesk@merces.nl)에 문의합니다. 다운로드한 **인증서(Base64)** 파일을 사용자의 이메일에 연결합니다. 또한 SSO 통합을 위해 구성할 수 있도록 **로그아웃 URL**, **SAML 엔터티 ID** 및 **SAML Single Sign-On 서비스 URL**을 제공합니다.

    > [!NOTE]
    >이 통합에는 **https://hr2day.force.com/INSTANCENAME** 패턴을 사용하여 설정되는 엔터티 ID가 필요하다고 Merces 팀에 알립니다.

    > [!TIP]
    >이제 앱을 설정하는 동안 [Azure Portal](https://portal.azure.com) 내에서 이러한 지침의 간결한 버전을 읽을 수 있습니다.  **Active Directory** > **엔터프라이즈 응용 프로그램** 섹션에서 이 앱을 추가한 후 **Single Sign-On** 탭을 선택합니다. 그런 다음 맨 아래에 있는 **구성** 섹션을 통해 포함된 설명서에 액세스합니다. 포함된 설명서 기능에 대한 자세한 내용은 [Azure AD 포함된 설명서]( https://go.microsoft.com/fwlink/?linkid=845985)에서 확인할 수 있습니다.
> 

### <a name="create-an-azure-ad-test-user"></a>Azure AD 테스트 사용자 만들기
이 섹션의 목적은 Azure Portal에서 Britta Simon이라는 테스트 사용자를 만드는 것입니다.

![Azure AD 사용자 만들기][100]

**Azure AD에서 테스트 사용자를 만들려면 다음 단계를 수행하세요.**

1. **Azure Portal**의 왼쪽 탐색 창에서 **Azure Active Directory** 아이콘을 선택합니다.

    ![Azure AD 테스트 사용자 만들기](./media/active-directory-saas-hr2day-tutorial/create_aaduser_01.png) 

2. 사용자 목록을 표시하려면 **사용자 및 그룹**으로 이동한 후 **모든 사용자**를 선택합니다.
    
    ![Azure AD 테스트 사용자 만들기](./media/active-directory-saas-hr2day-tutorial/create_aaduser_02.png) 

3. **사용자** 대화 상자를 열려면 대화 상자 위쪽에서 **추가**를 선택합니다.
 
    ![Azure AD 테스트 사용자 만들기](./media/active-directory-saas-hr2day-tutorial/create_aaduser_03.png) 

4. **사용자** 대화 상자에서 다음 단계를 수행합니다.
 
    ![Azure AD 테스트 사용자 만들기](./media/active-directory-saas-hr2day-tutorial/create_aaduser_04.png) 

    a. **이름** 상자에 **BrittaSimon**을 입력합니다.

    나. **사용자 이름** 상자에 BrittaSimon의 **이메일 주소**를 입력합니다.

    다. **암호 표시**를 선택한 다음 암호를 적어둡니다.

    d. **만들기**를 선택합니다.
 
### <a name="create-an-hr2day-by-merces-test-user"></a>HR2day by Merces 테스트 사용자 만들기

이 섹션의 목적은 HR2day by Merces에서 Britta Simon이라는 사용자를 만드는 것입니다. HR2day 계정에 사용자를 추가하려면 [HR2day by Merces 클라이언트 지원 팀](mailto:servicedesk@merces.nl)에 문의하세요. 

> [!NOTE]
> 사용자를 수동으로 생성해야 하는 경우 [HR2day by Merces 클라이언트 지원 팀](mailto:servicedesk@merces.nl)에 문의하세요.

### <a name="assign-the-azure-ad-test-user"></a>Azure AD 테스트 사용자 할당

이 섹션에서는 Azure Single Sign-On을 사용할 수 있도록 Britta Simon에게 HR2day by Merces에 대한 액세스 권한을 부여합니다.

![사용자 할당][200] 

**Britta Simon을 HR2day by Merces에 할당하려면 다음 단계를 수행합니다.**

1. Azure Portal에서 응용 프로그램 보기를 열고 디렉터리 보기로 이동한 다음 **엔터프라이즈 응용 프로그램**으로 이동합니다. 다음으로 **모든 응용 프로그램**을 선택합니다.

    ![사용자 할당][201] 

2. 응용 프로그램 목록에서 **HR2day by Merces**를 선택합니다.

    ![Single Sign-On 구성](./media/active-directory-saas-hr2day-tutorial/tutorial_hr2daybymerces_app.png) 

3. 왼쪽 메뉴에서 **사용자 및 그룹**을 선택합니다.

    ![사용자 할당][202] 

4. **추가** 단추를 선택합니다. 그런 후 **할당 추가** 대화 상자에서 **사용자 및 그룹**을 선택합니다.

    ![사용자 할당][203]

5. **사용자 및 그룹** 대화 상자의 **사용자 목록**에서 **Britta Simon**을 선택합니다.

6. **선택** 단추를 클릭합니다.

7. **할당 추가** 대화 상자에서 **할당**을 선택합니다.
    
### <a name="test-single-sign-on"></a>Single Sign-On 테스트

이 섹션은 액세스 패널을 사용하여 Azure AD Single Sign-On 구성을 테스트하기 위한 것입니다.  

액세스 패널에서 HR2day by Merces 타일을 선택하면 HR2day by Merces 응용 프로그램에 자동으로 로그인됩니다.

## <a name="additional-resources"></a>추가 리소스

* [Azure Active Directory와 SaaS 앱을 통합하는 방법에 대한 자습서 목록](active-directory-saas-tutorial-list.md)
* [Azure Active Directory로 응용 프로그램 액세스 및 Single Sign-On을 구현하는 방법](manage-apps/what-is-single-sign-on.md)



<!--Image references-->

[1]: ./media/active-directory-saas-hr2day-tutorial/tutorial_general_01.png
[2]: ./media/active-directory-saas-hr2day-tutorial/tutorial_general_02.png
[3]: ./media/active-directory-saas-hr2day-tutorial/tutorial_general_03.png
[4]: ./media/active-directory-saas-hr2day-tutorial/tutorial_general_04.png

[100]: ./media/active-directory-saas-hr2day-tutorial/tutorial_general_100.png

[200]: ./media/active-directory-saas-hr2day-tutorial/tutorial_general_200.png
[201]: ./media/active-directory-saas-hr2day-tutorial/tutorial_general_201.png
[202]: ./media/active-directory-saas-hr2day-tutorial/tutorial_general_202.png
[203]: ./media/active-directory-saas-hr2day-tutorial/tutorial_general_203.png

