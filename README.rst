
DART-FSS Tutorial
=================

Dart API Key 발급은 `DART OPEN
API <http://dart.fss.or.kr/dsap001/intro.do>`__\ 를 참고하시기 바랍니다.

1. OPEN API 인증
----------------

1.1 환경변수를 이용한 설정
~~~~~~~~~~~~~~~~~~~~~~~~~~

DART\_API\_KEY 환경 변수 설정시 자동으로 인증

.. code:: bash

    # Linux or Macos
    export DART_API_KEY=xxxxxxxxxxxxxxxxxxxxx

    # Windows
    set DART_API_KEY=xxxxxxxxxxxxxxxxxxxxx

1.2 dart\_set\_api\_key 함수를 이용한 설정
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: python

    import dart_fss as dart
    api_key= 'xxxxxxxxxxxxxxxxxxxxx'
    dart.dart_set_api_key(api_key=api_key)

2. 상장 종목 검색
-----------------

상장 종목 검색은 `KIND <http://kind.krx.co.kr>`__ 을 이용합니다.
이로인해 `KIND <http://kind.krx.co.kr>`__ 서버 유지보수시 검색이
불가능합니다

.. code:: ipython3

    import dart_fss as dart
    crp_list = dart.get_crp_list()
    crp_list




.. parsed-literal::

    Narket type: AllMkt
    Number of companies: 2273



.. code:: ipython3

    crp_list.find_by_name('삼성')




.. parsed-literal::

    [[006400]삼성SDI,
     [207940]삼성바이오로직스,
     [068290]삼성출판사,
     [029780]삼성카드,
     [000810]삼성화재해상보험,
     [018260]삼성에스디에스,
     [010140]삼성중공업,
     [016360]삼성증권,
     [028260]삼성물산,
     [005930]삼성전자,
     [001360]삼성제약,
     [006660]삼성공조,
     [032830]삼성생명,
     [009150]삼성전기,
     [028050]삼성엔지니어링,
     [309930]삼성머스트스팩3호,
     [291230]삼성스팩2호]



.. code:: ipython3

    crp_list.find_by_product('의약')




.. parsed-literal::

    [[003220]대원제약,
     [000640]동아쏘시오홀딩스,
     [207940]삼성바이오로직스,
     [019170]신풍제약,
     [004720]우리들제약,
     [033270]유나이티드,
     [249420]일동제약,
     [271980]제일약품,
     [002620]제일파마홀딩스,
     [128940]한미약품,
     [031390]녹십자셀,
     [142280]녹십자엠에스,
     [078140]대봉엘에스,
     [023910]대한약품,
     [206640]바디텍메드,
     [009300]삼아제약,
     [153710]옵티팜,
     [034940]조아제약,
     [166480]코아스템,
     [203690]프로스테믹스,
     [222980]한국맥널티,
     [200670]휴메딕스,
     [246250]에스엘에스바이오,
     [314130]지놈앤컴퍼니,
     [002250]알보젠코리아,
     [003520]영진약품,
     [000220]유유제약,
     [000100]유한양행,
     [185750]종근당,
     [011000]진원생명과학,
     [024720]한국콜마홀딩스,
     [016580]환인제약,
     [058820]CMG제약,
     [114450]KPX생명과학,
     [059210]메타바이오메드,
     [018680]서울제약,
     [065660]안트로젠,
     [174900]앱클론,
     [109960]에이프로젠 H&G,
     [183490]엔지켐생명과학,
     [206650]유바이오로직스,
     [263050]유틸렉스,
     [052670]제일바이오,
     [228760]지노믹트리,
     [041960]코미팜,
     [200130]콜마비앤에이치,
     [191420]테고사이언스,
     [222110]팬젠,
     [080720]한국유니온제약,
     [176750]듀켐바이오,
     [225220]제놀루션,
     [002720]국제약품,
     [069620]대웅제약,
     [017180]명문제약,
     [003120]일성신약,
     [063160]종근당바이오,
     [044820]코스맥스비티아이,
     [054670]대한뉴팜,
     [086900]메디톡스,
     [078160]메디포스트,
     [064550]바이오니아,
     [200780]비씨월드제약,
     [049180]셀루메드,
     [268600]셀리버리,
     [049960]쎌바이오텍,
     [086890]이수앱지스,
     [046210]파나진,
     [208340]파멥신,
     [145020]휴젤,
     [096760]JW홀딩스,
     [000020]동화약품,
     [001360]삼성제약,
     [000520]삼일제약,
     [005500]삼진제약,
     [068270]셀트리온,
     [293480]하나제약,
     [002390]한독,
     [138610]나이벡,
     [036480]대성미생물,
     [086450]동국제약,
     [053030]바이넥스,
     [068760]셀트리온제약,
     [096530]씨젠,
     [246720]아스타,
     [041910]에스텍파마,
     [187420]제노포커스,
     [241820]피씨엘,
     [097950]CJ제일제당,
     [096770]SK이노베이션,
     [006280]녹십자,
     [003000]부광약품,
     [008490]서흥,
     [000230]일동홀딩스,
     [217730]강스템바이오텍,
     [011040]경동제약,
     [000250]삼천당제약,
     [002800]신신제약,
     [260660]알리코제약,
     [072020]중앙백신,
     [214450]파마리서치프로덕트,
     [087010]펩트론,
     [106190]하이텍팜,
     [253840]수젠텍,
     [066830]제노텍,
     [234080]JW생명과학,
     [009290]광동제약,
     [003090]대웅,
     [002210]동성제약,
     [001630]종근당홀딩스,
     [161890]한국콜마,
     [009420]한올바이오파마,
     [067290]JW신약,
     [053950]경남제약,
     [067080]대화제약,
     [001540]안국약품,
     [237690]에스티팜,
     [182400]에이티젠,
     [290650]엘앤씨바이오,
     [018620]우진비앤지,
     [204840]지엘팜텍,
     [085660]차바이오텍,
     [066700]테라젠이텍스,
     [246710]티앤알바이오팹,
     [042520]한스바이오메드,
     [233250]메디안디노스틱,
     [281310]바이오시네틱스,
     [067370]선바이오,
     [001060]JW중외제약,
     [214390]경보제약,
     [003850]보령제약,
     [002630]오리엔트바이오,
     [102460]이연제약,
     [007570]일양약품,
     [005690]파미셀,
     [008930]한미사이언스,
     [014570]고려제약,
     [120240]대정화금,
     [131030]디에이치피코리아,
     [091990]셀트리온헬스케어,
     [175250]아이큐어,
     [196300]애니젠,
     [950130]엑세스바이오,
     [039200]오스코텍,
     [048530]인트론바이오,
     [278280]천보,
     [214370]케어젠,
     [102940]코오롱생명과학,
     [061250]화일약품,
     [205470]휴마시스,
     [243070]휴온스,
     [240340]인터코스,
     [303360]프로테옴텍,
     [170900]동아에스티,
     [003060]에이프로젠제약,
     [004310]현대약품,
     [006620]동구바이오제약,
     [086820]바이오솔루션,
     [100700]세운메디칼,
     [012790]신일제약,
     [298380]에이비엘바이오,
     [007370]진양제약,
     [950160]코오롱티슈진,
     [220100]퓨쳐켐,
     [262760]엔케이맥스]



.. code:: ipython3

    samsung_electronics = crp_list.find_by_crp_cd('005930')
    samsung_electronics




.. raw:: html

    
        <style scoped>
            .dart-table tbody tr th {
                vertical-align: top;
                text-overflow: ellipsis;
            }
            .dart-table thead th {
                text-align: right;
                text-overflow: ellipsis;
            }
        </style>
        <table border="1" class="dart-table"><thead><tr style="text-align: right;"><th>Label</th><th>Data</th></tr></thead><tbody><tr><th>crp_cd</th><td>005930<td></tr><tr><th>crp_nm</th><td>삼성전자(주)<td></tr><tr><th>crp_nm_e</th><td>SAMSUNG ELECTRONICS CO,.LTD<td></tr><tr><th>crp_nm_i</th><td>삼성전자<td></tr><tr><th>ceo_nm</th><td>김기남, 김현석, 고동진<td></tr><tr><th>crp_cls</th><td>Y<td></tr><tr><th>crp_no</th><td>1301110006246<td></tr><tr><th>bsn_no</th><td>1248100998<td></tr><tr><th>adr</th><td>경기도 수원시 영통구  삼성로 129 (매탄동)<td></tr><tr><th>hm_url</th><td>www.sec.co.kr<td></tr><tr><th>ir_url</th><td><td></tr><tr><th>phn_no</th><td>031-200-1114<td></tr><tr><th>fax_no</th><td>031-200-7538<td></tr><tr><th>ind_cd</th><td>264<td></tr><tr><th>est_dt</th><td>19690113<td></tr><tr><th>acc_mt</th><td>12<td></tr><tr><th>crp_ctp</th><td>통신 및 방송 장비 제조업<td></tr><tr><th>crp_prod</th><td>IMT2000 서비스용 동기식 기지국,교환국장비,데이터단말기,동영상휴대폰,핵심칩,반도체제품,사무,계산 및 회계용기계<td></tr></tbody></table>



3. Dart 공시조회
----------------

3.1 주의사항
~~~~~~~~~~~~

dart-fss 패키지는 dart.fss.or.kr의 오픈 API 방식을 이용하여 검색을
진행하고 있으나, JSON 반환 방식을 이용하고 있기 때문에 오류가
발생하더라도 응답결과는 항상 정상으로 표시되는 상태입니다.

동일한 검색 요청에 대하여 XML 반환 방식은 정상적으로 오류를 표시하나
JSON 방식은 정상으로 표시하는 상태입니다.

.. code:: ipython3

    import requests

.. code:: ipython3

    url_xml = r'http://dart.fss.or.kr/api/search.xml?auth=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx&crp_cd=1'
    resp = requests.get(url_xml)
    print(resp.text)


.. parsed-literal::

    <?xml version="1.0" encoding="utf-8"?>
    <result>
      <err_code>010</err_code>
      <err_msg>미등록 인증키</err_msg>
      <page_no>1</page_no>
      <page_set>10</page_set>
      <total_count>0</total_count>
      <total_page>0</total_page>
    </result>
    

.. code:: ipython3

    url_xml = r'http://dart.fss.or.kr/api/search.json?auth=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx&crp_cd=1'
    resp = requests.get(url_xml)
    print(resp.text)


.. parsed-literal::

    {"err_code":"000","err_msg":"정상","page_no":1,"page_set":10,"total_count":0,"total_page":0,"list":[]}
    

3.2 공시조회
~~~~~~~~~~~~

당일 공시 정보 조회는 Parameter 없이 검색하면 가능합니다

.. code:: ipython3

    from dart_fss import search_report
    reports = search_report() 
    reports




.. raw:: html

    
        <style scoped>
            .dart-table tbody tr th {
                vertical-align: top;
                text-overflow: ellipsis;
            }
            .dart-table thead th {
                text-align: right;
                text-overflow: ellipsis;
            }
        </style>
        <table border="1" class="dart-table"><thead><tr style="text-align: right;"><th>Label</th><th>Data</th></tr></thead><tbody><tr><th>page_no</th><td>1<td></tr><tr><th>page_set</th><td>10<td></tr><tr><th>total_count</th><td>99<td></tr><tr><th>total_page</th><td>10<td></tr><tr><th>report_list</th><td><table><thead><tr><th></th><th>crp_cls</th><th>crp_nm</th><th>crp_cd</th><th>rpt_nm</th><th>rcp_no</th><th>flr_nm</th><th>rcp_dt</th><th>rmk</th></tr></thead><tbody><tr><th>0</th><td>E</td><td>신한금융투자</td><td>00138321</td><td>증권발행실적보고서</td><td>20190419000161</td><td>신한금융투자</td><td>20190419</td><td></td></tr><tr><th>1</th><td>Y</td><td>엔피씨</td><td>004250</td><td>임원ㆍ주요주주특정증권등소유상황보고서</td><td>20190419000157</td><td>한국투자밸류자산운용</td><td>20190419</td><td></td></tr><tr><th>2</th><td>E</td><td>한화에스비아이기업인수목적</td><td>01351822</td><td>[기재정정]투자설명서</td><td>20190419000156</td><td>한화에스비아이기업인수목적</td><td>20190419</td><td></td></tr><tr><th>3</th><td>E</td><td>케이비증권</td><td>00164876</td><td>일괄신고추가서류(기타파생결합증권)</td><td>20190419000159</td><td>케이비증권</td><td>20190419</td><td></td></tr><tr><th>4</th><td>Y</td><td>교보증권</td><td>030610</td><td>투자설명서(일괄신고)</td><td>20190419000154</td><td>교보증권</td><td>20190419</td><td></td></tr><tr><th>5</th><td>E</td><td>한화에스비아이기업인수목적</td><td>01351822</td><td>[발행조건확정]증권신고서(지분증권)</td><td>20190419000153</td><td>한화에스비아이기업인수목적</td><td>20190419</td><td></td></tr><tr><th>6</th><td>Y</td><td>교보증권</td><td>030610</td><td>투자설명서(일괄신고)</td><td>20190419000152</td><td>교보증권</td><td>20190419</td><td></td></tr><tr><th>7</th><td>E</td><td>에이치디씨자산운용</td><td>00405463</td><td>철회신고서(HDC트와이스리자드지수연계증권투자신탁SHE-33호(ELS-파생형))</td><td>20190419000150</td><td>에이치디씨자산운용</td><td>20190419</td><td></td></tr><tr><th>8</th><td>E</td><td>신한금융투자</td><td>00138321</td><td>증권발행실적보고서</td><td>20190419000149</td><td>신한금융투자</td><td>20190419</td><td></td></tr><tr><th>9</th><td>K</td><td>소프트센</td><td>032680</td><td>주식등의대량보유상황보고서(약식)</td><td>20190419000148</td><td>김재홍</td><td>20190419</td><td></td></tr></tbody></table></td></tr></tbody></table>



.. code:: ipython3

    # 다음페이지로 이동
    reports.next_page()
    # 이전페이지로 이동
    reports.prev_page()
    reports




.. raw:: html

    
        <style scoped>
            .dart-table tbody tr th {
                vertical-align: top;
                text-overflow: ellipsis;
            }
            .dart-table thead th {
                text-align: right;
                text-overflow: ellipsis;
            }
        </style>
        <table border="1" class="dart-table"><thead><tr style="text-align: right;"><th>Label</th><th>Data</th></tr></thead><tbody><tr><th>page_no</th><td>1<td></tr><tr><th>page_set</th><td>10<td></tr><tr><th>total_count</th><td>98<td></tr><tr><th>total_page</th><td>10<td></tr><tr><th>report_list</th><td><table><thead><tr><th></th><th>crp_cls</th><th>crp_nm</th><th>crp_cd</th><th>rpt_nm</th><th>rcp_no</th><th>flr_nm</th><th>rcp_dt</th><th>rmk</th></tr></thead><tbody><tr><th>0</th><td>E</td><td>신한금융투자</td><td>00138321</td><td>증권발행실적보고서</td><td>20190419000161</td><td>신한금융투자</td><td>20190419</td><td></td></tr><tr><th>1</th><td>Y</td><td>엔피씨</td><td>004250</td><td>임원ㆍ주요주주특정증권등소유상황보고서</td><td>20190419000157</td><td>한국투자밸류자산운용</td><td>20190419</td><td></td></tr><tr><th>2</th><td>E</td><td>한화에스비아이기업인수목적</td><td>01351822</td><td>[기재정정]투자설명서</td><td>20190419000156</td><td>한화에스비아이기업인수목적</td><td>20190419</td><td></td></tr><tr><th>3</th><td>E</td><td>케이비증권</td><td>00164876</td><td>일괄신고추가서류(기타파생결합증권)</td><td>20190419000159</td><td>케이비증권</td><td>20190419</td><td></td></tr><tr><th>4</th><td>Y</td><td>교보증권</td><td>030610</td><td>투자설명서(일괄신고)</td><td>20190419000154</td><td>교보증권</td><td>20190419</td><td></td></tr><tr><th>5</th><td>E</td><td>한화에스비아이기업인수목적</td><td>01351822</td><td>[발행조건확정]증권신고서(지분증권)</td><td>20190419000153</td><td>한화에스비아이기업인수목적</td><td>20190419</td><td></td></tr><tr><th>6</th><td>Y</td><td>교보증권</td><td>030610</td><td>투자설명서(일괄신고)</td><td>20190419000152</td><td>교보증권</td><td>20190419</td><td></td></tr><tr><th>7</th><td>E</td><td>에이치디씨자산운용</td><td>00405463</td><td>철회신고서(HDC트와이스리자드지수연계증권투자신탁SHE-33호(ELS-파생형))</td><td>20190419000150</td><td>에이치디씨자산운용</td><td>20190419</td><td></td></tr><tr><th>8</th><td>E</td><td>신한금융투자</td><td>00138321</td><td>증권발행실적보고서</td><td>20190419000149</td><td>신한금융투자</td><td>20190419</td><td></td></tr><tr><th>9</th><td>K</td><td>소프트센</td><td>032680</td><td>주식등의대량보유상황보고서(약식)</td><td>20190419000148</td><td>김재홍</td><td>20190419</td><td></td></tr></tbody></table></td></tr></tbody></table>



.. code:: ipython3

    # 한번에 보이는 페이지수 변경
    reports.page_set = 100
    reports




.. raw:: html

    
        <style scoped>
            .dart-table tbody tr th {
                vertical-align: top;
                text-overflow: ellipsis;
            }
            .dart-table thead th {
                text-align: right;
                text-overflow: ellipsis;
            }
        </style>
        <table border="1" class="dart-table"><thead><tr style="text-align: right;"><th>Label</th><th>Data</th></tr></thead><tbody><tr><th>page_no</th><td>1<td></tr><tr><th>page_set</th><td>100<td></tr><tr><th>total_count</th><td>98<td></tr><tr><th>total_page</th><td>1<td></tr><tr><th>report_list</th><td><table><thead><tr><th></th><th>crp_cls</th><th>crp_nm</th><th>crp_cd</th><th>rpt_nm</th><th>rcp_no</th><th>flr_nm</th><th>rcp_dt</th><th>rmk</th></tr></thead><tbody><tr><th>0</th><td>E</td><td>신한금융투자</td><td>00138321</td><td>증권발행실적보고서</td><td>20190419000161</td><td>신한금융투자</td><td>20190419</td><td></td></tr><tr><th>1</th><td>Y</td><td>엔피씨</td><td>004250</td><td>임원ㆍ주요주주특정증권등소유상황보고서</td><td>20190419000157</td><td>한국투자밸류자산운용</td><td>20190419</td><td></td></tr><tr><th>2</th><td>E</td><td>한화에스비아이기업인수목적</td><td>01351822</td><td>[기재정정]투자설명서</td><td>20190419000156</td><td>한화에스비아이기업인수목적</td><td>20190419</td><td></td></tr><tr><th>3</th><td>E</td><td>케이비증권</td><td>00164876</td><td>일괄신고추가서류(기타파생결합증권)</td><td>20190419000159</td><td>케이비증권</td><td>20190419</td><td></td></tr><tr><th>4</th><td>Y</td><td>교보증권</td><td>030610</td><td>투자설명서(일괄신고)</td><td>20190419000154</td><td>교보증권</td><td>20190419</td><td></td></tr><tr><th>5</th><td>E</td><td>한화에스비아이기업인수목적</td><td>01351822</td><td>[발행조건확정]증권신고서(지분증권)</td><td>20190419000153</td><td>한화에스비아이기업인수목적</td><td>20190419</td><td></td></tr><tr><th>6</th><td>Y</td><td>교보증권</td><td>030610</td><td>투자설명서(일괄신고)</td><td>20190419000152</td><td>교보증권</td><td>20190419</td><td></td></tr><tr><th>7</th><td>E</td><td>에이치디씨자산운용</td><td>00405463</td><td>철회신고서(HDC트와이스리자드지수연계증권투자신탁SHE-33호(ELS-파생형))</td><td>20190419000150</td><td>에이치디씨자산운용</td><td>20190419</td><td></td></tr><tr><th>8</th><td>E</td><td>신한금융투자</td><td>00138321</td><td>증권발행실적보고서</td><td>20190419000149</td><td>신한금융투자</td><td>20190419</td><td></td></tr><tr><th>9</th><td>K</td><td>소프트센</td><td>032680</td><td>주식등의대량보유상황보고서(약식)</td><td>20190419000148</td><td>김재홍</td><td>20190419</td><td></td></tr><tr><th>10</th><td>Y</td><td>경인양행</td><td>012610</td><td>임원ㆍ주요주주특정증권등소유상황보고서</td><td>20190419000147</td><td>이상호</td><td>20190419</td><td></td></tr><tr><th>11</th><td>Y</td><td>미래에셋대우</td><td>006800</td><td>투자설명서(일괄신고)</td><td>20190419000146</td><td>미래에셋대우</td><td>20190419</td><td></td></tr><tr><th>12</th><td>K</td><td>한컴유니맥스</td><td>215090</td><td>주식등의대량보유상황보고서(일반)</td><td>20190419000145</td><td>한컴MDS</td><td>20190419</td><td></td></tr><tr><th>13</th><td>E</td><td>신한금융투자</td><td>00138321</td><td>증권발행실적보고서</td><td>20190419000144</td><td>신한금융투자</td><td>20190419</td><td></td></tr><tr><th>14</th><td>Y</td><td>아모레퍼시픽그룹</td><td>002790</td><td>최대주주등소유주식변동신고서</td><td>20190419800246</td><td>아모레퍼시픽그룹</td><td>20190419</td><td>유</td></tr><tr><th>15</th><td>Y</td><td>삼성증권</td><td>016360</td><td>증권발행실적보고서</td><td>20190419000141</td><td>삼성증권</td><td>20190419</td><td></td></tr><tr><th>16</th><td>Y</td><td>삼성증권</td><td>016360</td><td>증권발행실적보고서</td><td>20190419000140</td><td>삼성증권</td><td>20190419</td><td></td></tr><tr><th>17</th><td>Y</td><td>삼성증권</td><td>016360</td><td>증권발행실적보고서</td><td>20190419000139</td><td>삼성증권</td><td>20190419</td><td></td></tr><tr><th>18</th><td>E</td><td>진우엔지니어링</td><td>00246833</td><td>[기재정정]감사보고서 (2018.12)</td><td>20190419000138</td><td>미래회계법인</td><td>20190419</td><td></td></tr><tr><th>19</th><td>E</td><td>포렉스</td><td>00832658</td><td>[기재정정]감사보고서 (2018.12)</td><td>20190419000136</td><td>호연회계법인</td><td>20190419</td><td></td></tr><tr><th>20</th><td>E</td><td>라톤코리아</td><td>00618720</td><td>연결감사보고서 (2018.12)</td><td>20190419000131</td><td>회계법인예원</td><td>20190419</td><td></td></tr><tr><th>21</th><td>N</td><td>줌인터넷</td><td>229480</td><td>기업설명회(IR)개최</td><td>20190419600231</td><td>줌인터넷</td><td>20190419</td><td>넥</td></tr><tr><th>22</th><td>E</td><td>동원엔터프라이즈</td><td>00360425</td><td>특수관계인과의내부거래</td><td>20190419000123</td><td>동원엔터프라이즈</td><td>20190419</td><td>공</td></tr><tr><th>23</th><td>K</td><td>슈펙스비앤피</td><td>058530</td><td>주식등의대량보유상황보고서(일반)</td><td>20190419000122</td><td>트라이던트</td><td>20190419</td><td></td></tr><tr><th>24</th><td>N</td><td>줌인터넷</td><td>229480</td><td>임시주주총회결과</td><td>20190419600228</td><td>줌인터넷</td><td>20190419</td><td>넥</td></tr><tr><th>25</th><td>K</td><td>피제이전자</td><td>006140</td><td>임원ㆍ주요주주특정증권등소유상황보고서</td><td>20190419000121</td><td>김재석</td><td>20190419</td><td></td></tr><tr><th>26</th><td>E</td><td>우민</td><td>01159057</td><td>연결감사보고서 (2018.12)</td><td>20190419000120</td><td>오성회계법인</td><td>20190419</td><td></td></tr><tr><th>27</th><td>K</td><td>뷰웍스</td><td>100120</td><td>연결재무제표기준영업(잠정)실적(공정공시)</td><td>20190419900224</td><td>뷰웍스</td><td>20190419</td><td>코</td></tr><tr><th>28</th><td>K</td><td>피제이전자</td><td>006140</td><td>주식등의대량보유상황보고서(일반)</td><td>20190419000119</td><td>김재석</td><td>20190419</td><td></td></tr><tr><th>29</th><td>E</td><td>협신</td><td>00813608</td><td>감사보고서 (2018.12)</td><td>20190419000118</td><td>세신공인회계사감사반(제199호)</td><td>20190419</td><td></td></tr><tr><th>30</th><td>E</td><td>대원지주회사</td><td>00428206</td><td>연결감사보고서 (2018.12)</td><td>20190419000107</td><td>선우회계법인</td><td>20190419</td><td></td></tr><tr><th>31</th><td>K</td><td>슈펙스비앤피</td><td>058530</td><td>[기재정정]최대주주변경을수반하는주식담보제공계약체결</td><td>20190419900214</td><td>슈펙스비앤피</td><td>20190419</td><td>코</td></tr><tr><th>32</th><td>Y</td><td>현대건설</td><td>000720</td><td>결산실적공시예고(안내공시)</td><td>20190419800213</td><td>현대건설</td><td>20190419</td><td>유</td></tr><tr><th>33</th><td>Y</td><td>교보증권</td><td>030610</td><td>일괄신고추가서류(파생결합증권-주가연계증권)</td><td>20190419000108</td><td>교보증권</td><td>20190419</td><td></td></tr><tr><th>34</th><td>Y</td><td>신라교역</td><td>004970</td><td>최대주주등소유주식변동신고서</td><td>20190419800212</td><td>신라교역</td><td>20190419</td><td>유</td></tr><tr><th>35</th><td>K</td><td>미래에셋제5호스팩</td><td>239340</td><td>상호변경안내</td><td>20190419900211</td><td>미래에셋제5호스팩</td><td>20190419</td><td>코</td></tr><tr><th>36</th><td>E</td><td>대일개발</td><td>00217910</td><td>연결감사보고서 (2018.12)</td><td>20190419000099</td><td>삼덕회계법인</td><td>20190419</td><td></td></tr><tr><th>37</th><td>Y</td><td>미래에셋대우</td><td>006800</td><td>투자설명서(일괄신고)</td><td>20190419000096</td><td>미래에셋대우</td><td>20190419</td><td></td></tr><tr><th>38</th><td>Y</td><td>고려개발</td><td>004200</td><td>결산실적공시예고(안내공시)</td><td>20190419800199</td><td>고려개발</td><td>20190419</td><td>유</td></tr><tr><th>39</th><td>Y</td><td>미래에셋대우</td><td>006800</td><td>일괄신고추가서류(파생결합증권-주가연계증권)</td><td>20190419000128</td><td>미래에셋대우</td><td>20190419</td><td></td></tr><tr><th>40</th><td>Y</td><td>일성건설</td><td>013360</td><td>타인에대한채무보증결정</td><td>20190419800196</td><td>일성건설</td><td>20190419</td><td>유</td></tr><tr><th>41</th><td>Y</td><td>교보증권</td><td>030610</td><td>일괄신고추가서류(기타파생결합사채)</td><td>20190419000111</td><td>교보증권</td><td>20190419</td><td></td></tr><tr><th>42</th><td>K</td><td>한컴유니맥스</td><td>215090</td><td>주식등의대량보유상황보고서(약식)</td><td>20190419000093</td><td>알패트론</td><td>20190419</td><td></td></tr><tr><th>43</th><td>Y</td><td>NH투자증권</td><td>005940</td><td>증권발행실적보고서</td><td>20190419000092</td><td>NH투자증권</td><td>20190419</td><td></td></tr><tr><th>44</th><td>E</td><td>한국투자증권</td><td>00160144</td><td>투자설명서(일괄신고)</td><td>20190419000091</td><td>한국투자증권</td><td>20190419</td><td></td></tr><tr><th>45</th><td>K</td><td>뉴프라이드</td><td>900100</td><td>감사보고서제출</td><td>20190419900184</td><td>뉴프라이드</td><td>20190419</td><td>코</td></tr><tr><th>46</th><td>K</td><td>솔브레인</td><td>036830</td><td>신탁계약해지결과보고서</td><td>20190419000087</td><td>솔브레인</td><td>20190419</td><td></td></tr><tr><th>47</th><td>K</td><td>미래에셋제5호스팩</td><td>239340</td><td>임시주주총회결과</td><td>20190419900179</td><td>미래에셋제5호스팩</td><td>20190419</td><td>코</td></tr><tr><th>48</th><td>Y</td><td>SK하이닉스</td><td>000660</td><td>임원ㆍ주요주주특정증권등소유상황보고서</td><td>20190419000084</td><td>강선국</td><td>20190419</td><td></td></tr><tr><th>49</th><td>E</td><td>한국투자증권</td><td>00160144</td><td>일괄신고추가서류(파생결합증권-주가연계증권)</td><td>20190419000085</td><td>한국투자증권</td><td>20190419</td><td></td></tr><tr><th>50</th><td>K</td><td>와이오엠</td><td>066430</td><td>기업설명회(IR)개최</td><td>20190419900174</td><td>와이오엠</td><td>20190419</td><td>코</td></tr><tr><th>51</th><td>K</td><td>솔브레인</td><td>036830</td><td>주요사항보고서(자기주식취득신탁계약해지결정)</td><td>20190419000083</td><td>솔브레인</td><td>20190419</td><td></td></tr><tr><th>52</th><td>Y</td><td>미래에셋대우</td><td>006800</td><td>투자설명서(일괄신고)</td><td>20190419000081</td><td>미래에셋대우</td><td>20190419</td><td></td></tr><tr><th>53</th><td>E</td><td>유빈스홀딩스</td><td>01076709</td><td>특수관계인으로부터자금차입</td><td>20190419000077</td><td>유빈스홀딩스</td><td>20190419</td><td>공</td></tr><tr><th>54</th><td>Y</td><td>미래에셋대우</td><td>006800</td><td>일괄신고추가서류(파생결합증권-주가연계증권)</td><td>20190419000086</td><td>미래에셋대우</td><td>20190419</td><td></td></tr><tr><th>55</th><td>E</td><td>이츠게임즈</td><td>01204825</td><td>임원의변동</td><td>20190419000071</td><td>이츠게임즈</td><td>20190419</td><td>공</td></tr><tr><th>56</th><td>K</td><td>칩스앤미디어</td><td>094360</td><td>결산실적공시예고</td><td>20190419900159</td><td>칩스앤미디어</td><td>20190419</td><td>코</td></tr><tr><th>57</th><td>E</td><td>삼동</td><td>00199359</td><td>연결감사보고서 (2018.12)</td><td>20190419000068</td><td>한울회계법인</td><td>20190419</td><td></td></tr><tr><th>58</th><td>E</td><td>에이앤티에스</td><td>00605656</td><td>특수관계인에대한자금대여</td><td>20190419000067</td><td>에이앤티에스</td><td>20190419</td><td>공</td></tr><tr><th>59</th><td>Y</td><td>메리츠종금증권</td><td>008560</td><td>투자설명서(일괄신고)</td><td>20190419000065</td><td>메리츠종금증권</td><td>20190419</td><td></td></tr><tr><th>60</th><td>K</td><td>모두투어</td><td>080160</td><td>임원ㆍ주요주주특정증권등소유상황보고서</td><td>20190419000064</td><td>우준열</td><td>20190419</td><td></td></tr><tr><th>61</th><td>Y</td><td>미래에셋대우</td><td>006800</td><td>투자설명서(일괄신고)</td><td>20190419000062</td><td>미래에셋대우</td><td>20190419</td><td></td></tr><tr><th>62</th><td>Y</td><td>NH투자증권</td><td>005940</td><td>증권발행실적보고서</td><td>20190419000060</td><td>NH투자증권</td><td>20190419</td><td></td></tr><tr><th>63</th><td>K</td><td>코스온</td><td>069110</td><td>전환가액의조정</td><td>20190419900149</td><td>코스온</td><td>20190419</td><td>코</td></tr><tr><th>64</th><td>K</td><td>시공테크</td><td>020710</td><td>단일판매ㆍ공급계약체결</td><td>20190419900148</td><td>시공테크</td><td>20190419</td><td>코</td></tr><tr><th>65</th><td>Y</td><td>유안타증권</td><td>003470</td><td>증권발행실적보고서</td><td>20190419000058</td><td>유안타증권</td><td>20190419</td><td></td></tr><tr><th>66</th><td>E</td><td>나눔기술</td><td>00259828</td><td>[기재정정]사업보고서 (2018.12)</td><td>20190419000057</td><td>나눔기술</td><td>20190419</td><td></td></tr><tr><th>67</th><td>Y</td><td>대림통상</td><td>006570</td><td>최대주주등소유주식변동신고서</td><td>20190419800142</td><td>대림통상</td><td>20190419</td><td>유</td></tr><tr><th>68</th><td>E</td><td>에스엘비코리아</td><td>01328444</td><td>감사보고서 (2018.12)</td><td>20190419000056</td><td>오성회계법인</td><td>20190419</td><td></td></tr><tr><th>69</th><td>E</td><td>동원</td><td>00414212</td><td>연결감사보고서 (2018.12)</td><td>20190419000055</td><td>정진회계법인</td><td>20190419</td><td></td></tr><tr><th>70</th><td>E</td><td>대영베이스</td><td>00606309</td><td>연결감사보고서 (2018.12)</td><td>20190419000053</td><td>중원공인회계사감사반(제212호)</td><td>20190419</td><td></td></tr><tr><th>71</th><td>Y</td><td>삼성증권</td><td>016360</td><td>투자설명서(일괄신고)</td><td>20190419000051</td><td>삼성증권</td><td>20190419</td><td></td></tr><tr><th>72</th><td>Y</td><td>삼성증권</td><td>016360</td><td>투자설명서(일괄신고)</td><td>20190419000050</td><td>삼성증권</td><td>20190419</td><td></td></tr><tr><th>73</th><td>Y</td><td>대림통상</td><td>006570</td><td>임원ㆍ주요주주특정증권등소유상황보고서</td><td>20190419000049</td><td>이효진</td><td>20190419</td><td></td></tr><tr><th>74</th><td>K</td><td>오이솔루션</td><td>138080</td><td>단일판매ㆍ공급계약체결</td><td>20190419900128</td><td>오이솔루션</td><td>20190419</td><td>코</td></tr><tr><th>75</th><td>Y</td><td>유안타증권</td><td>003470</td><td>증권발행실적보고서</td><td>20190419000044</td><td>유안타증권</td><td>20190419</td><td></td></tr><tr><th>76</th><td>E</td><td>현대드림투어</td><td>00575841</td><td>[기재정정]임원의변동</td><td>20190419000040</td><td>현대드림투어</td><td>20190419</td><td>공</td></tr><tr><th>77</th><td>E</td><td>세우실업</td><td>00532493</td><td>동일인등출자계열회사와의상품ㆍ용역거래변경</td><td>20190419000039</td><td>세우실업</td><td>20190419</td><td>공</td></tr><tr><th>78</th><td>E</td><td>동주</td><td>00118585</td><td>동일인등출자계열회사와의상품ㆍ용역거래변경</td><td>20190419000037</td><td>동주</td><td>20190419</td><td>공</td></tr><tr><th>79</th><td>E</td><td>한화도시개발</td><td>00798682</td><td>임원의변동</td><td>20190419000035</td><td>한화도시개발</td><td>20190419</td><td>공</td></tr><tr><th>80</th><td>E</td><td>경기용인테크노밸리</td><td>01095333</td><td>임원의변동</td><td>20190419000034</td><td>경기용인테크노밸리</td><td>20190419</td><td>공</td></tr><tr><th>81</th><td>Y</td><td>두산인프라코어</td><td>042670</td><td>결산실적공시예고(안내공시)</td><td>20190419800073</td><td>두산인프라코어</td><td>20190419</td><td>유</td></tr><tr><th>82</th><td>Y</td><td>미래에셋대우</td><td>006800</td><td>일괄신고추가서류(파생결합증권-주가연계증권)</td><td>20190419000063</td><td>미래에셋대우</td><td>20190419</td><td></td></tr><tr><th>83</th><td>E</td><td>에이치밸리</td><td>00824622</td><td>임원의변동</td><td>20190419000033</td><td>에이치밸리</td><td>20190419</td><td>공</td></tr><tr><th>84</th><td>E</td><td>아산테크노밸리</td><td>00596482</td><td>임원의변동</td><td>20190419000032</td><td>아산테크노밸리</td><td>20190419</td><td>공</td></tr><tr><th>85</th><td>Y</td><td>삼성증권</td><td>016360</td><td>일괄신고추가서류(기타파생결합증권)</td><td>20190419000045</td><td>삼성증권</td><td>20190419</td><td></td></tr><tr><th>86</th><td>Y</td><td>한국항공우주</td><td>047810</td><td>[기재정정]사업보고서 (2018.12)</td><td>20190419000031</td><td>한국항공우주</td><td>20190419</td><td>연</td></tr><tr><th>87</th><td>Y</td><td>미래에셋대우</td><td>006800</td><td>일괄신고추가서류(기타파생결합증권)</td><td>20190419000030</td><td>미래에셋대우</td><td>20190419</td><td></td></tr><tr><th>88</th><td>Y</td><td>삼성증권</td><td>016360</td><td>일괄신고추가서류(파생결합증권-주가연계증권)</td><td>20190419000046</td><td>삼성증권</td><td>20190419</td><td></td></tr><tr><th>89</th><td>Y</td><td>메리츠종금증권</td><td>008560</td><td>일괄신고추가서류(파생결합증권-주가연계증권)</td><td>20190419000048</td><td>메리츠종금증권</td><td>20190419</td><td></td></tr><tr><th>90</th><td>E</td><td>광주방송</td><td>00218627</td><td>특수관계인으로부터자금차입</td><td>20190419000019</td><td>광주방송</td><td>20190419</td><td>공</td></tr><tr><th>91</th><td>E</td><td>케이비씨플러스</td><td>01242700</td><td>특수관계인에대한자금대여</td><td>20190419000017</td><td>케이비씨플러스</td><td>20190419</td><td>공</td></tr><tr><th>92</th><td>Y</td><td>교보증권</td><td>030610</td><td>일괄신고추가서류(파생결합사채-주가연계파생결합사채)</td><td>20190419000114</td><td>교보증권</td><td>20190419</td><td></td></tr><tr><th>93</th><td>Y</td><td>SK네트웍스</td><td>001740</td><td>투자설명서</td><td>20190419000009</td><td>SK네트웍스</td><td>20190419</td><td></td></tr><tr><th>94</th><td>Y</td><td>흥아해운</td><td>003280</td><td>주주총회소집공고</td><td>20190419000001</td><td>흥아해운</td><td>20190419</td><td></td></tr><tr><th>95</th><td>Y</td><td>SK네트웍스</td><td>001740</td><td>효력발생안내( 2019.4.9. 제출 증권신고서(채무증권) )</td><td>20190409100002</td><td>금융감독원</td><td>20190419</td><td></td></tr><tr><th>96</th><td>E</td><td>신화전선</td><td>00830599</td><td>감사보고서 (2018.12)</td><td>20190418000559</td><td>위드회계법인</td><td>20190419</td><td></td></tr><tr><th>97</th><td>K</td><td>한컴유니맥스</td><td>215090</td><td>주식등의대량보유상황보고서(약식)</td><td>20190418000558</td><td>라카이코리아</td><td>20190419</td><td></td></tr></tbody></table></td></tr></tbody></table>



.. code:: ipython3

    # 10번째 공시정보 선택
    reports[10]




.. raw:: html

    
        <style scoped>
            .dart-table tbody tr th {
                vertical-align: top;
                text-overflow: ellipsis;
            }
            .dart-table thead th {
                text-align: right;
                text-overflow: ellipsis;
            }
        </style>
        <table border="1" class="dart-table"><thead><tr style="text-align: right;"><th>Label</th><th>Data</th></tr></thead><tbody><tr><th>crp_cls</th><td>Y<td></tr><tr><th>crp_nm</th><td>경인양행<td></tr><tr><th>crp_cd</th><td>012610<td></tr><tr><th>rpt_nm</th><td>임원ㆍ주요주주특정증권등소유상황보고서<td></tr><tr><th>rcp_no</th><td>20190419000147<td></tr><tr><th>flr_nm</th><td>이상호<td></tr><tr><th>rcp_dt</th><td>20190419<td></tr><tr><th>rmk</th><td><td></tr><tr><th>pages</th><td>Not loaded<td></tr></tbody></table>



    공시정보는 기본적으로 내부 내용들을 로딩되지 않은 생태로 전달된다.
    이는 기본적인 정보들만 불러온 상태에서 추가적인 세부 정보가
    필요한경우 page\_load 함수 또는 pages를 호출하는 순간 세부 정보들을
    불러오게된다

.. code:: ipython3

    # pages loading
    reports[10].pages


.. parsed-literal::

                                                    



.. parsed-literal::

    [{'ele_id': 0, 'rcp_no': '20190419000147', 'title': '전체'},
     {'ele_id': '1', 'rcp_no': '20190419000147', 'title': '임원ㆍ주요주주특정증권등소유상황보고서'},
     {'ele_id': '2', 'rcp_no': '20190419000147', 'title': '1.발행회사에관한사항'},
     {'ele_id': '3', 'rcp_no': '20190419000147', 'title': '2.보고자에관한사항'},
     {'ele_id': '4', 'rcp_no': '20190419000147', 'title': '3.특정증권등의소유상황'}]



.. code:: ipython3

    # page 로딩이후에는 모든 정보들이 로딩된다
    reports[10]




.. raw:: html

    
        <style scoped>
            .dart-table tbody tr th {
                vertical-align: top;
                text-overflow: ellipsis;
            }
            .dart-table thead th {
                text-align: right;
                text-overflow: ellipsis;
            }
        </style>
        <table border="1" class="dart-table"><thead><tr style="text-align: right;"><th>Label</th><th>Data</th></tr></thead><tbody><tr><th>crp_cls</th><td>Y<td></tr><tr><th>crp_nm</th><td>경인양행<td></tr><tr><th>crp_cd</th><td>012610<td></tr><tr><th>rpt_nm</th><td>임원ㆍ주요주주특정증권등소유상황보고서<td></tr><tr><th>rcp_no</th><td>20190419000147<td></tr><tr><th>flr_nm</th><td>이상호<td></tr><tr><th>rcp_dt</th><td>20190419<td></tr><tr><th>rmk</th><td><td></tr><tr><th>pages</th><td><table><thead><tr><th></th><th>title</th><th>rcp_no</th><th>ele_id</th></tr></thead><tbody><tr><th>0</th><td>전체</td><td>20190419000147</td><td>0</td></tr><tr><th>1</th><td>임원ㆍ주요주주특정증권등소유상황보고서</td><td>20190419000147</td><td>1</td></tr><tr><th>2</th><td>1.발행회사에관한사항</td><td>20190419000147</td><td>2</td></tr><tr><th>3</th><td>2.보고자에관한사항</td><td>20190419000147</td><td>3</td></tr><tr><th>4</th><td>3.특정증권등의소유상황</td><td>20190419000147</td><td>4</td></tr></tbody></table></td></tr></tbody></table>



.. code:: ipython3

    # 리포트의 특정 Page 불러오기
    reports[10][2]
    # 리포트의 Raw HTML을 보기 위해서는 reports[10][2].html 처럼 불러오면 된다.




.. raw:: html

    <iframe src="data:text/html;base64,PCFET0NUWVBFIEhUTUwgUFVCTElDICItLy9XM0MvL0RURCBIVE1MIDQuMDEgVHJhbnNpdGlvbmFsLy9FTiIgImh0dHA6Ly93d3cudzMub3JnL1RSL2h0bWw0L2xvb3NlLmR0ZCI+Cgo8aHRtbCBzdHlsZT0iYm9yZGVyOjAiPgo8aGVhZD4KPHRpdGxlPjwvdGl0bGU+CjxtZXRhIGNvbnRlbnQ9IklFPUVtdWxhdGVJRTgiIGh0dHAtZXF1aXY9IlgtVUEtQ29tcGF0aWJsZSIvPgo8bWV0YSBjb250ZW50PSJnZGkiIGh0dHAtZXF1aXY9IlgtVUEtVGV4dExheW91dE1ldHJpY3MiLz4KPG1ldGEgY29udGVudD0idGV4dC9odG1sOyBjaGFyc2V0PXV0Zi04IiBodHRwLWVxdWl2PSJDb250ZW50LVR5cGUiLz4KPGxpbmsgaHJlZj0iaHR0cDovL2RhcnQuZnNzLm9yLmtyL2Nzcy9yZXBvcnRfeG1sLmNzcyIgcmVsPSJzdHlsZXNoZWV0IiB0eXBlPSJ0ZXh0L2NzcyIvPgo8L2hlYWQ+Cjxib2R5IGJnY29sb3I9IiNGRkZGRkYiPgo8cD48YnIvPjwvcD4KPHAgY2xhc3M9InNlY3Rpb24tMiI+PGEgbmFtZT0idG9jMSI+MS4g67Cc7ZaJ7ZqM7IKs7JeQIOq0gO2VnCDsgqztla08L2E+PC9wPgo8dGFibGUgYm9yZGVyPSIxIiB3aWR0aD0iNjAwIj4KPGNvbGdyb3VwPgo8Y29sIHdpZHRoPSIxNTAiLz4KPGNvbCB3aWR0aD0iMTM3Ii8+Cjxjb2wgd2lkdGg9IjE2MyIvPgo8Y29sIHdpZHRoPSIxNTAiLz4KPC9jb2xncm91cD4KPHRib2R5Pgo8dHI+Cjx0ZCBhbGlnbj0iQ0VOVEVSIiBoZWlnaHQ9IjIwIiB3aWR0aD0iMTUwIj7tmowg7IKsIOuqhTwvdGQ+Cjx0ZCBjb2xzcGFuPSIzIiBoZWlnaHQ9IjIwIiB3aWR0aD0iNDUwIj4gKOyjvCnqsr3snbjslpHtlok8L3RkPgo8L3RyPgo8dHI+Cjx0ZCBhbGlnbj0iQ0VOVEVSIiBoZWlnaHQ9IjIwIiB3aWR0aD0iMTUwIj7rspXsnbjqtazrtoQ8L3RkPgo8dGQgYWxpZ249IkNFTlRFUiIgaGVpZ2h0PSIyMCIgd2lkdGg9IjEzNyI+7Jyg6rCA7Kad6raM7IOB7J6l67KV7J24PC90ZD4KPHRkIGFsaWduPSJDRU5URVIiIGhlaWdodD0iMjAiIHdpZHRoPSIxNjMiPu2ajOyCrOy9lOuTnCA8L3RkPgo8dGQgYWxpZ249IkNFTlRFUiIgaGVpZ2h0PSIyMCIgd2lkdGg9IjE1MCI+MDEyNjEwPC90ZD4KPC90cj4KPHRyPgo8dGQgYWxpZ249IkNFTlRFUiIgaGVpZ2h0PSIyMCIgd2lkdGg9IjE1MCI+67Cc7ZaJ7KO87IudIOy0neyImDwvdGQ+Cjx0ZCBhbGlnbj0iQ0VOVEVSIiBjb2xzcGFuPSIzIiBoZWlnaHQ9IjIwIiB3aWR0aD0iNDUwIj40MCwzOTYsMzY1PC90ZD4KPC90cj4KPC90Ym9keT4KPC90YWJsZT4KPHA+PGJyLz48L3A+CjxwPjxici8+PC9wPgo8L2JvZHk+CjwvaHRtbD4=" style="width:100%; height:500px;"></iframe>



.. code:: ipython3

    # 현재 실행되는 디렉토리에 './회사명/보고서명/' 안에 HTML 파일 형태로 저장
    # 파일 저장 위치를 설정하기 위해서는 .to_path(path) 형태로 사용
    reports[10].to_file()


.. parsed-literal::

    Save files: 100%|██████████| 5/5 [00:00<00:00, 622.50page/s]
    

4. Dart 공시데이터 기반 재무제표 추출
-------------------------------------

4.1 연결 재무상태표
~~~~~~~~~~~~~~~~~~~

.. code:: ipython3

    samsung_electronics.get_financial_statement(start_dt='20120101')


.. parsed-literal::

    Download: 31.0KB [00:00, 195KB/s]
    Loading report - annual: 100%|██████████| 7/7 [00:06<00:00,  1.08page/s]
    



.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>concept_id</th>
          <th>label_ko</th>
          <th>label_en</th>
          <th>class0</th>
          <th>class1</th>
          <th>class2</th>
          <th>class3</th>
          <th>class4</th>
          <th>[2018-12-31]연결재무제표</th>
          <th>[2017-12-31]연결재무제표</th>
          <th>[2016-12-31]연결재무제표</th>
          <th>[2015-12-31]연결재무제표</th>
          <th>[2014-12-31]연결재무제표</th>
          <th>[2013-12-31]연결재무제표</th>
          <th>[2012-12-31]연결재무제표</th>
          <th>[2011-12-31]연결재무제표</th>
          <th>[2010-12-31]연결재무제표</th>
          <th>[2009-12-31]연결재무제표</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>ifrs_CurrentAssets</td>
          <td>유동자산</td>
          <td>Current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>None</td>
          <td>None</td>
          <td>174,697,424,000,000.0</td>
          <td>146,982,464,000,000.0</td>
          <td>141,429,704,000,000.0</td>
          <td>124,814,725,000,000.0</td>
          <td>115,146,026,000,000.0</td>
          <td>110,760,271,000,000.0</td>
          <td>87,269,017,000,000.0</td>
          <td>71,502,063,000,000.0</td>
          <td>61,402,589,000,000.0</td>
          <td>54,211,297,000,000.0</td>
        </tr>
        <tr>
          <th>1</th>
          <td>ifrs_CashAndCashEquivalents</td>
          <td>현금및현금성자산</td>
          <td>Cash and cash equivalents</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>현금및현금성자산</td>
          <td>None</td>
          <td>30,340,505,000,000.0</td>
          <td>30,545,130,000,000.0</td>
          <td>32,111,442,000,000.0</td>
          <td>22,636,744,000,000.0</td>
          <td>16,840,766,000,000.0</td>
          <td>16,284,780,000,000.0</td>
          <td>18,791,460,000,000.0</td>
          <td>14,691,761,000,000.0</td>
          <td>9,791,419,000,000.0</td>
          <td>10,149,930,000,000.0</td>
        </tr>
        <tr>
          <th>2</th>
          <td>dart_ShortTermDepositsNotClassifiedAsCashEquiv...</td>
          <td>단기금융상품</td>
          <td>Short-term financial instruments</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>단기금융상품</td>
          <td>None</td>
          <td>65,893,797,000,000.0</td>
          <td>49,447,696,000,000.0</td>
          <td>52,432,411,000,000.0</td>
          <td>44,228,800,000,000.0</td>
          <td>41,689,776,000,000.0</td>
          <td>36,722,702,000,000.0</td>
          <td>17,397,937,000,000.0</td>
          <td>11,529,905,000,000.0</td>
          <td>11,529,392,000,000.0</td>
          <td>8,629,113,000,000.0</td>
        </tr>
        <tr>
          <th>3</th>
          <td>entity00126380_udf_BS_20171018214525642_Curren...</td>
          <td>단기매도가능금융자산</td>
          <td>Available-for-sale financial assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>단기매도가능금융자산</td>
          <td>None</td>
          <td>nan</td>
          <td>3,191,375,000,000.0</td>
          <td>3,638,460,000,000.0</td>
          <td>4,627,530,000,000.0</td>
          <td>3,286,798,000,000.0</td>
          <td>1,488,527,000,000.0</td>
          <td>1,258,874,000,000.0</td>
          <td>655,969,000,000.0</td>
          <td>1,159,152,000,000.0</td>
          <td>2,104,420,000,000.0</td>
        </tr>
        <tr>
          <th>4</th>
          <td>entity00126380_udf_BS_201851017339116_CurrentA...</td>
          <td>단기상각후원가금융자산</td>
          <td>after depreciation capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>단기상각후원가금융자산</td>
          <td>None</td>
          <td>2,703,693,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>5</th>
          <td>entity00126380_udf_BS_201931110524523_CurrentA...</td>
          <td>단기당기손익-공정가치금융자산</td>
          <td>income-fair value capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>단기당기손익-공정가치금융자산</td>
          <td>None</td>
          <td>2,001,948,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>6</th>
          <td>dart_ShortTermTradeReceivable</td>
          <td>매출채권</td>
          <td>Short-term trade Receivable</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>매출채권</td>
          <td>None</td>
          <td>33,867,733,000,000.0</td>
          <td>27,695,995,000,000.0</td>
          <td>24,279,211,000,000.0</td>
          <td>25,168,026,000,000.0</td>
          <td>24,694,610,000,000.0</td>
          <td>24,988,532,000,000.0</td>
          <td>23,861,235,000,000.0</td>
          <td>21,882,127,000,000.0</td>
          <td>19,153,114,000,000.0</td>
          <td>17,818,740,000,000.0</td>
        </tr>
        <tr>
          <th>7</th>
          <td>entity00126380_udf_BS_201710182279121_CurrentA...</td>
          <td>미수금</td>
          <td>Other account receivables</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>미수금</td>
          <td>None</td>
          <td>3,080,733,000,000.0</td>
          <td>4,108,961,000,000.0</td>
          <td>3,521,197,000,000.0</td>
          <td>3,352,663,000,000.0</td>
          <td>3,539,875,000,000.0</td>
          <td>2,887,402,000,000.0</td>
          <td>2,813,361,000,000.0</td>
          <td>2,270,901,000,000.0</td>
          <td>2,155,720,000,000.0</td>
          <td>1,978,039,000,000.0</td>
        </tr>
        <tr>
          <th>8</th>
          <td>entity00126380_udf_BS_20171018221011173_Curren...</td>
          <td>선급금</td>
          <td>Advance payment</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>선급금</td>
          <td>None</td>
          <td>1,361,807,000,000.0</td>
          <td>1,753,673,000,000.0</td>
          <td>1,439,938,000,000.0</td>
          <td>1,706,003,000,000.0</td>
          <td>1,989,470,000,000.0</td>
          <td>1,928,188,000,000.0</td>
          <td>1,674,428,000,000.0</td>
          <td>1,436,288,000,000.0</td>
          <td>1,302,428,000,000.0</td>
          <td>1,566,921,000,000.0</td>
        </tr>
        <tr>
          <th>9</th>
          <td>entity00126380_udf_BS_2017101822109437_Current...</td>
          <td>선급비용</td>
          <td>Prepaid expense</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>선급비용</td>
          <td>None</td>
          <td>4,136,167,000,000.0</td>
          <td>3,835,219,000,000.0</td>
          <td>3,502,083,000,000.0</td>
          <td>3,170,632,000,000.0</td>
          <td>3,346,593,000,000.0</td>
          <td>2,472,950,000,000.0</td>
          <td>2,262,234,000,000.0</td>
          <td>2,329,463,000,000.0</td>
          <td>2,200,739,000,000.0</td>
          <td>1,460,449,000,000.0</td>
        </tr>
        <tr>
          <th>10</th>
          <td>ifrs_Inventories</td>
          <td>재고자산</td>
          <td>Inventories</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>재고자산</td>
          <td>None</td>
          <td>28,984,704,000,000.0</td>
          <td>24,983,355,000,000.0</td>
          <td>18,353,503,000,000.0</td>
          <td>18,811,794,000,000.0</td>
          <td>17,317,504,000,000.0</td>
          <td>19,134,868,000,000.0</td>
          <td>17,747,413,000,000.0</td>
          <td>15,716,715,000,000.0</td>
          <td>13,364,524,000,000.0</td>
          <td>9,839,329,000,000.0</td>
        </tr>
        <tr>
          <th>11</th>
          <td>dart_OtherCurrentAssets</td>
          <td>기타유동자산</td>
          <td>Other current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>기타유동자산</td>
          <td>None</td>
          <td>2,326,337,000,000.0</td>
          <td>1,421,060,000,000.0</td>
          <td>1,315,653,000,000.0</td>
          <td>1,035,460,000,000.0</td>
          <td>1,795,143,000,000.0</td>
          <td>2,135,589,000,000.0</td>
          <td>1,462,075,000,000.0</td>
          <td>988,934,000,000.0</td>
          <td>746,101,000,000.0</td>
          <td>664,356,000,000.0</td>
        </tr>
        <tr>
          <th>12</th>
          <td>ifrs_NoncurrentAssetsOrDisposalGroupsClassifie...</td>
          <td>매각예정분류자산</td>
          <td>Non-current assets or disposal groups classifi...</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>매각예정분류자산</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>835,806,000,000.0</td>
          <td>77,073,000,000.0</td>
          <td>645,491,000,000.0</td>
          <td>2,716,733,000,000.0</td>
          <td>nan</td>
          <td>0.0</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>13</th>
          <td>ifrs_NoncurrentAssets</td>
          <td>비유동자산</td>
          <td>Non-current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>None</td>
          <td>None</td>
          <td>164,659,820,000,000.0</td>
          <td>154,769,626,000,000.0</td>
          <td>120,744,620,000,000.0</td>
          <td>117,364,796,000,000.0</td>
          <td>115,276,932,000,000.0</td>
          <td>103,314,747,000,000.0</td>
          <td>93,802,553,000,000.0</td>
          <td>84,298,200,000,000.0</td>
          <td>72,906,214,000,000.0</td>
          <td>57,968,492,000,000.0</td>
        </tr>
        <tr>
          <th>14</th>
          <td>dart_LongTermDepositsNotClassifiedAsCashEquiva...</td>
          <td>장기매도가능금융자산</td>
          <td>Long-term deposits not classified as cash equi...</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>장기매도가능금융자산</td>
          <td>None</td>
          <td>nan</td>
          <td>7,752,180,000,000.0</td>
          <td>6,804,276,000,000.0</td>
          <td>8,332,480,000,000.0</td>
          <td>12,667,509,000,000.0</td>
          <td>6,238,380,000,000.0</td>
          <td>5,229,175,000,000.0</td>
          <td>3,223,598,000,000.0</td>
          <td>3,040,206,000,000.0</td>
          <td>1,489,138,000,000.0</td>
        </tr>
        <tr>
          <th>15</th>
          <td>entity00126380_udf_BS_20182211113197_Noncurren...</td>
          <td>만기보유금융자산</td>
          <td>Held-to-maturity</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>만기보유금융자산</td>
          <td>None</td>
          <td>nan</td>
          <td>106,751,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>16</th>
          <td>entity00126380_udf_BS_20185101782898_Noncurren...</td>
          <td>상각후원가금융자산</td>
          <td>after depreciation capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>상각후원가금융자산</td>
          <td>None</td>
          <td>238,309,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>17</th>
          <td>entity00126380_udf_BS_201851017830322_Noncurre...</td>
          <td>기타포괄손익-공정가치금융자산</td>
          <td>oci-fair value capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>기타포괄손익-공정가치금융자산</td>
          <td>None</td>
          <td>7,301,351,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>18</th>
          <td>entity00126380_udf_BS_201851017832579_Noncurre...</td>
          <td>당기손익-공정가치금융자산</td>
          <td>income-fair value capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>당기손익-공정가치금융자산</td>
          <td>None</td>
          <td>775,427,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>19</th>
          <td>entity00126380_udf_BS_20171018221637438_Noncur...</td>
          <td>관계기업 및 공동기업 투자</td>
          <td>Availalble for sale financial asset associates...</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>관계기업 및 공동기업 투자</td>
          <td>None</td>
          <td>7,313,206,000,000.0</td>
          <td>6,802,351,000,000.0</td>
          <td>5,837,884,000,000.0</td>
          <td>5,276,348,000,000.0</td>
          <td>5,232,461,000,000.0</td>
          <td>6,422,292,000,000.0</td>
          <td>8,785,489,000,000.0</td>
          <td>9,204,169,000,000.0</td>
          <td>8,335,290,000,000.0</td>
          <td>7,334,705,000,000.0</td>
        </tr>
        <tr>
          <th>20</th>
          <td>ifrs_PropertyPlantAndEquipment</td>
          <td>유형자산</td>
          <td>Property, plant and equipment</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>유형자산</td>
          <td>None</td>
          <td>115,416,724,000,000.0</td>
          <td>111,665,648,000,000.0</td>
          <td>91,473,041,000,000.0</td>
          <td>86,477,110,000,000.0</td>
          <td>80,872,950,000,000.0</td>
          <td>75,496,388,000,000.0</td>
          <td>68,484,743,000,000.0</td>
          <td>62,043,951,000,000.0</td>
          <td>52,964,594,000,000.0</td>
          <td>43,560,295,000,000.0</td>
        </tr>
        <tr>
          <th>21</th>
          <td>ifrs_InvestmentProperty</td>
          <td>무형자산</td>
          <td>Investment property</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>무형자산</td>
          <td>None</td>
          <td>14,891,598,000,000.0</td>
          <td>14,760,483,000,000.0</td>
          <td>5,344,020,000,000.0</td>
          <td>5,396,311,000,000.0</td>
          <td>4,785,473,000,000.0</td>
          <td>3,980,600,000,000.0</td>
          <td>3,729,705,000,000.0</td>
          <td>3,355,236,000,000.0</td>
          <td>2,779,439,000,000.0</td>
          <td>1,256,008,000,000.0</td>
        </tr>
        <tr>
          <th>22</th>
          <td>dart_LongTermPrepaidExpenses</td>
          <td>장기선급비용</td>
          <td>Long-term prepaid expenses</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>장기선급비용</td>
          <td>None</td>
          <td>5,009,679,000,000.0</td>
          <td>3,434,375,000,000.0</td>
          <td>3,834,831,000,000.0</td>
          <td>4,294,401,000,000.0</td>
          <td>4,857,126,000,000.0</td>
          <td>3,465,783,000,000.0</td>
          <td>3,515,479,000,000.0</td>
          <td>3,454,205,000,000.0</td>
          <td>3,544,572,000,000.0</td>
          <td>2,440,608,000,000.0</td>
        </tr>
        <tr>
          <th>23</th>
          <td>dart_DepositsForSeveranceInsurance</td>
          <td>순확정급여자산</td>
          <td>Deposits for severance insurance</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>순확정급여자산</td>
          <td>None</td>
          <td>562,356,000,000.0</td>
          <td>825,892,000,000.0</td>
          <td>557,091,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>24</th>
          <td>ifrs_DeferredTaxAssets</td>
          <td>이연법인세자산</td>
          <td>Deferred tax assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>이연법인세자산</td>
          <td>None</td>
          <td>5,468,002,000,000.0</td>
          <td>5,061,687,000,000.0</td>
          <td>5,321,450,000,000.0</td>
          <td>5,589,108,000,000.0</td>
          <td>4,526,595,000,000.0</td>
          <td>4,621,780,000,000.0</td>
          <td>2,516,080,000,000.0</td>
          <td>1,783,086,000,000.0</td>
          <td>1,144,068,000,000.0</td>
          <td>1,051,601,000,000.0</td>
        </tr>
        <tr>
          <th>25</th>
          <td>dart_OtherNonCurrentAssets</td>
          <td>기타비유동자산</td>
          <td>Other non-current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>기타비유동자산</td>
          <td>None</td>
          <td>7,683,168,000,000.0</td>
          <td>4,360,259,000,000.0</td>
          <td>1,572,027,000,000.0</td>
          <td>1,999,038,000,000.0</td>
          <td>2,334,818,000,000.0</td>
          <td>3,089,524,000,000.0</td>
          <td>1,541,882,000,000.0</td>
          <td>1,233,955,000,000.0</td>
          <td>442,383,000,000.0</td>
          <td>253,989,000,000.0</td>
        </tr>
        <tr>
          <th>26</th>
          <td>ifrs_Assets</td>
          <td>자산총계</td>
          <td>Total assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>자산총계</td>
          <td>None</td>
          <td>None</td>
          <td>339,357,244,000,000.0</td>
          <td>301,752,090,000,000.0</td>
          <td>262,174,324,000,000.0</td>
          <td>242,179,521,000,000.0</td>
          <td>230,422,958,000,000.0</td>
          <td>214,075,018,000,000.0</td>
          <td>181,071,570,000,000.0</td>
          <td>155,800,263,000,000.0</td>
          <td>134,308,803,000,000.0</td>
          <td>112,179,789,000,000.0</td>
        </tr>
        <tr>
          <th>27</th>
          <td>ifrs_CurrentLiabilities</td>
          <td>유동부채</td>
          <td>Current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>None</td>
          <td>None</td>
          <td>69,081,510,000,000.0</td>
          <td>67,175,114,000,000.0</td>
          <td>54,704,095,000,000.0</td>
          <td>50,502,909,000,000.0</td>
          <td>52,013,913,000,000.0</td>
          <td>51,315,409,000,000.0</td>
          <td>46,933,052,000,000.0</td>
          <td>44,319,014,000,000.0</td>
          <td>39,944,721,000,000.0</td>
          <td>34,204,424,000,000.0</td>
        </tr>
        <tr>
          <th>28</th>
          <td>entity00126380_udf_BS_20171018222617796_Curren...</td>
          <td>매입채무</td>
          <td>Account payable Trade</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>매입채무</td>
          <td>None</td>
          <td>8,479,916,000,000.0</td>
          <td>9,083,907,000,000.0</td>
          <td>6,485,039,000,000.0</td>
          <td>6,187,291,000,000.0</td>
          <td>7,914,704,000,000.0</td>
          <td>8,437,139,000,000.0</td>
          <td>9,489,111,000,000.0</td>
          <td>10,276,727,000,000.0</td>
          <td>9,148,661,000,000.0</td>
          <td>8,235,140,000,000.0</td>
        </tr>
        <tr>
          <th>29</th>
          <td>ifrs_ShorttermBorrowings</td>
          <td>단기차입금</td>
          <td>Short-term borrowings</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>단기차입금</td>
          <td>None</td>
          <td>13,586,660,000,000.0</td>
          <td>15,767,619,000,000.0</td>
          <td>12,746,789,000,000.0</td>
          <td>11,155,425,000,000.0</td>
          <td>8,029,299,000,000.0</td>
          <td>6,438,517,000,000.0</td>
          <td>8,443,752,000,000.0</td>
          <td>9,653,722,000,000.0</td>
          <td>8,429,721,000,000.0</td>
          <td>7,780,007,000,000.0</td>
        </tr>
        <tr>
          <th>30</th>
          <td>entity00126380_udf_BS_20171018222642264_Curren...</td>
          <td>미지급금</td>
          <td>Other payble</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>미지급금</td>
          <td>None</td>
          <td>10,711,536,000,000.0</td>
          <td>13,899,633,000,000.0</td>
          <td>11,525,910,000,000.0</td>
          <td>8,864,378,000,000.0</td>
          <td>10,318,407,000,000.0</td>
          <td>9,196,566,000,000.0</td>
          <td>7,400,239,000,000.0</td>
          <td>8,232,763,000,000.0</td>
          <td>6,901,139,000,000.0</td>
          <td>5,307,486,000,000.0</td>
        </tr>
        <tr>
          <th>31</th>
          <td>entity00126380_udf_BS_20171018222640707_Curren...</td>
          <td>선수금</td>
          <td>Advance received</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>선수금</td>
          <td>None</td>
          <td>820,265,000,000.0</td>
          <td>1,249,174,000,000.0</td>
          <td>1,358,878,000,000.0</td>
          <td>1,343,432,000,000.0</td>
          <td>1,427,230,000,000.0</td>
          <td>1,706,313,000,000.0</td>
          <td>1,517,672,000,000.0</td>
          <td>1,450,733,000,000.0</td>
          <td>883,585,000,000.0</td>
          <td>1,283,314,000,000.0</td>
        </tr>
        <tr>
          <th>32</th>
          <td>entity00126380_udf_BS_20171018222637261_Curren...</td>
          <td>예수금</td>
          <td>Withholdings</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>예수금</td>
          <td>None</td>
          <td>951,254,000,000.0</td>
          <td>793,582,000,000.0</td>
          <td>685,028,000,000.0</td>
          <td>992,733,000,000.0</td>
          <td>1,161,635,000,000.0</td>
          <td>1,176,046,000,000.0</td>
          <td>966,374,000,000.0</td>
          <td>1,715,070,000,000.0</td>
          <td>1,052,555,000,000.0</td>
          <td>844,918,000,000.0</td>
        </tr>
        <tr>
          <th>33</th>
          <td>entity00126380_udf_BS_20171018222635206_Curren...</td>
          <td>미지급비용</td>
          <td>Accrued expense</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>미지급비용</td>
          <td>None</td>
          <td>20,339,687,000,000.0</td>
          <td>13,996,273,000,000.0</td>
          <td>12,527,300,000,000.0</td>
          <td>11,628,739,000,000.0</td>
          <td>12,876,777,000,000.0</td>
          <td>11,344,530,000,000.0</td>
          <td>9,495,156,000,000.0</td>
          <td>7,823,728,000,000.0</td>
          <td>7,102,427,000,000.0</td>
          <td>5,945,348,000,000.0</td>
        </tr>
        <tr>
          <th>34</th>
          <td>dart_PaymentsOfIncomeTaxesPayable</td>
          <td>미지급법인세</td>
          <td>Payments of income taxes payable</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>미지급법인세</td>
          <td>None</td>
          <td>8,720,050,000,000.0</td>
          <td>7,408,348,000,000.0</td>
          <td>2,837,353,000,000.0</td>
          <td>3,401,625,000,000.0</td>
          <td>2,161,109,000,000.0</td>
          <td>3,386,018,000,000.0</td>
          <td>3,222,934,000,000.0</td>
          <td>1,262,798,000,000.0</td>
          <td>2,051,452,000,000.0</td>
          <td>1,124,423,000,000.0</td>
        </tr>
        <tr>
          <th>35</th>
          <td>entity00126380_udf_BS_20171024141934989_Curren...</td>
          <td>유동성장기부채</td>
          <td>Current portion of long-term borrowings and de...</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>유동성장기부채</td>
          <td>None</td>
          <td>33,386,000,000.0</td>
          <td>278,619,000,000.0</td>
          <td>1,232,817,000,000.0</td>
          <td>221,548,000,000.0</td>
          <td>1,778,667,000,000.0</td>
          <td>2,425,831,000,000.0</td>
          <td>999,010,000,000.0</td>
          <td>30,292,000,000.0</td>
          <td>1,123,934,000,000.0</td>
          <td>234,327,000,000.0</td>
        </tr>
        <tr>
          <th>36</th>
          <td>ifrs_CurrentProvisions</td>
          <td>충당부채</td>
          <td>Current provisions</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>충당부채</td>
          <td>None</td>
          <td>4,384,038,000,000.0</td>
          <td>4,294,820,000,000.0</td>
          <td>4,597,417,000,000.0</td>
          <td>6,420,603,000,000.0</td>
          <td>5,991,510,000,000.0</td>
          <td>6,736,476,000,000.0</td>
          <td>5,054,853,000,000.0</td>
          <td>3,514,536,000,000.0</td>
          <td>2,917,919,000,000.0</td>
          <td>3,205,865,000,000.0</td>
        </tr>
        <tr>
          <th>37</th>
          <td>dart_OtherCurrentLiabilities</td>
          <td>기타유동부채</td>
          <td>Other current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>기타유동부채</td>
          <td>None</td>
          <td>1,054,718,000,000.0</td>
          <td>403,139,000,000.0</td>
          <td>351,176,000,000.0</td>
          <td>287,135,000,000.0</td>
          <td>326,259,000,000.0</td>
          <td>467,973,000,000.0</td>
          <td>343,951,000,000.0</td>
          <td>358,645,000,000.0</td>
          <td>333,328,000,000.0</td>
          <td>243,596,000,000.0</td>
        </tr>
        <tr>
          <th>38</th>
          <td>ifrs_LiabilitiesIncludedInDisposalGroupsClassi...</td>
          <td>매각예정분류부채</td>
          <td>Liabilities included in disposal groups classi...</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>매각예정분류부채</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>356,388,000,000.0</td>
          <td>nan</td>
          <td>28,316,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>39</th>
          <td>ifrs_NoncurrentLiabilities</td>
          <td>비유동부채</td>
          <td>Non-current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>None</td>
          <td>None</td>
          <td>22,522,557,000,000.0</td>
          <td>20,085,548,000,000.0</td>
          <td>14,507,196,000,000.0</td>
          <td>12,616,807,000,000.0</td>
          <td>10,320,857,000,000.0</td>
          <td>12,743,599,000,000.0</td>
          <td>12,658,312,000,000.0</td>
          <td>10,167,619,000,000.0</td>
          <td>5,186,446,000,000.0</td>
          <td>4,930,163,000,000.0</td>
        </tr>
        <tr>
          <th>40</th>
          <td>dart_BondsIssued</td>
          <td>사채</td>
          <td>Bonds issued</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>사채</td>
          <td>None</td>
          <td>961,972,000,000.0</td>
          <td>953,361,000,000.0</td>
          <td>58,542,000,000.0</td>
          <td>1,230,448,000,000.0</td>
          <td>1,355,882,000,000.0</td>
          <td>1,311,068,000,000.0</td>
          <td>1,829,374,000,000.0</td>
          <td>1,280,124,000,000.0</td>
          <td>587,338,000,000.0</td>
          <td>224,183,000,000.0</td>
        </tr>
        <tr>
          <th>41</th>
          <td>dart_LongTermBorrowingsGross</td>
          <td>장기차입금</td>
          <td>Long-term borrowings, gross</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>장기차입금</td>
          <td>None</td>
          <td>85,085,000,000.0</td>
          <td>1,814,446,000,000.0</td>
          <td>1,244,238,000,000.0</td>
          <td>266,542,000,000.0</td>
          <td>101,671,000,000.0</td>
          <td>985,117,000,000.0</td>
          <td>3,623,028,000,000.0</td>
          <td>3,682,472,000,000.0</td>
          <td>634,381,000,000.0</td>
          <td>1,156,094,000,000.0</td>
        </tr>
        <tr>
          <th>42</th>
          <td>dart_LongTermOtherPayablesGross</td>
          <td>장기미지급금</td>
          <td>Long-Term other Payables, gross</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>장기미지급금</td>
          <td>None</td>
          <td>3,194,043,000,000.0</td>
          <td>2,043,729,000,000.0</td>
          <td>3,317,054,000,000.0</td>
          <td>3,041,687,000,000.0</td>
          <td>2,562,271,000,000.0</td>
          <td>1,053,756,000,000.0</td>
          <td>1,165,881,000,000.0</td>
          <td>1,024,804,000,000.0</td>
          <td>1,072,661,000,000.0</td>
          <td>1,120,982,000,000.0</td>
        </tr>
        <tr>
          <th>43</th>
          <td>dart_PostemploymentBenefitObligations</td>
          <td>순확정급여부채</td>
          <td>Post-employment benefit obligations</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>순확정급여부채</td>
          <td>None</td>
          <td>504,064,000,000.0</td>
          <td>389,922,000,000.0</td>
          <td>173,656,000,000.0</td>
          <td>358,820,000,000.0</td>
          <td>201,342,000,000.0</td>
          <td>1,854,902,000,000.0</td>
          <td>1,729,939,000,000.0</td>
          <td>1,119,188,000,000.0</td>
          <td>823,486,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>44</th>
          <td>ifrs_DeferredTaxLiabilities</td>
          <td>이연법인세부채</td>
          <td>Deferred tax liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>이연법인세부채</td>
          <td>None</td>
          <td>15,162,523,000,000.0</td>
          <td>11,710,781,000,000.0</td>
          <td>7,293,514,000,000.0</td>
          <td>5,154,792,000,000.0</td>
          <td>4,097,811,000,000.0</td>
          <td>6,012,371,000,000.0</td>
          <td>3,429,467,000,000.0</td>
          <td>2,333,442,000,000.0</td>
          <td>1,618,523,000,000.0</td>
          <td>1,249,964,000,000.0</td>
        </tr>
        <tr>
          <th>45</th>
          <td>dart_LongTermTradeAndOtherNonCurrentPayables</td>
          <td>장기충당부채</td>
          <td>Long-term trade and other non-current payables</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>장기충당부채</td>
          <td>None</td>
          <td>663,619,000,000.0</td>
          <td>464,324,000,000.0</td>
          <td>358,126,000,000.0</td>
          <td>522,378,000,000.0</td>
          <td>499,290,000,000.0</td>
          <td>460,924,000,000.0</td>
          <td>408,529,000,000.0</td>
          <td>363,223,000,000.0</td>
          <td>295,357,000,000.0</td>
          <td>244,443,000,000.0</td>
        </tr>
        <tr>
          <th>46</th>
          <td>dart_OtherNonCurrentLiabilities</td>
          <td>기타비유동부채</td>
          <td>Other non-current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>기타비유동부채</td>
          <td>None</td>
          <td>1,951,251,000,000.0</td>
          <td>2,708,985,000,000.0</td>
          <td>2,062,066,000,000.0</td>
          <td>2,042,140,000,000.0</td>
          <td>1,502,590,000,000.0</td>
          <td>1,065,461,000,000.0</td>
          <td>472,094,000,000.0</td>
          <td>364,366,000,000.0</td>
          <td>31,187,000,000.0</td>
          <td>31,587,000,000.0</td>
        </tr>
        <tr>
          <th>47</th>
          <td>ifrs_Liabilities</td>
          <td>부채총계</td>
          <td>Total liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>부채총계</td>
          <td>None</td>
          <td>None</td>
          <td>91,604,067,000,000.0</td>
          <td>87,260,662,000,000.0</td>
          <td>69,211,291,000,000.0</td>
          <td>63,119,716,000,000.0</td>
          <td>62,334,770,000,000.0</td>
          <td>64,059,008,000,000.0</td>
          <td>59,591,364,000,000.0</td>
          <td>54,486,633,000,000.0</td>
          <td>45,131,167,000,000.0</td>
          <td>39,134,587,000,000.0</td>
        </tr>
        <tr>
          <th>48</th>
          <td>ifrs_EquityAttributableToOwnersOfParent</td>
          <td>지배기업 소유주지분</td>
          <td>Equity attributable to owners of parent</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>None</td>
          <td>None</td>
          <td>240,068,993,000,000.0</td>
          <td>207,213,416,000,000.0</td>
          <td>186,424,328,000,000.0</td>
          <td>172,876,767,000,000.0</td>
          <td>162,181,725,000,000.0</td>
          <td>144,442,616,000,000.0</td>
          <td>117,094,052,000,000.0</td>
          <td>97,090,383,000,000.0</td>
          <td>85,441,561,000,000.0</td>
          <td>69,565,053,000,000.0</td>
        </tr>
        <tr>
          <th>49</th>
          <td>ifrs_IssuedCapital</td>
          <td>자본금</td>
          <td>Issued capital</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>자본금</td>
          <td>None</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
        </tr>
        <tr>
          <th>50</th>
          <td>dart_IssuedCapitalOfPreferredStock</td>
          <td>우선주자본금</td>
          <td>Issued capital of preferred stock</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>자본금</td>
          <td>우선주자본금</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
        </tr>
        <tr>
          <th>51</th>
          <td>dart_IssuedCapitalOfCommonStock</td>
          <td>보통주자본금</td>
          <td>Issued capital of common stock</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>자본금</td>
          <td>보통주자본금</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
        </tr>
        <tr>
          <th>52</th>
          <td>ifrs_SharePremium</td>
          <td>주식발행초과금</td>
          <td>Share premium</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>주식발행초과금</td>
          <td>None</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
        </tr>
        <tr>
          <th>53</th>
          <td>ifrs_RetainedEarnings</td>
          <td>이익잉여금</td>
          <td>Retained earnings</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>이익잉여금</td>
          <td>None</td>
          <td>242,698,956,000,000.0</td>
          <td>215,811,200,000,000.0</td>
          <td>193,086,317,000,000.0</td>
          <td>185,132,014,000,000.0</td>
          <td>169,529,604,000,000.0</td>
          <td>148,600,282,000,000.0</td>
          <td>119,985,689,000,000.0</td>
          <td>97,622,872,000,000.0</td>
          <td>85,071,444,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>54</th>
          <td>dart_ElementsOfOtherStockholdersEquity</td>
          <td>기타자본항목</td>
          <td>Elements of other stockholder's equity</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>기타자본항목</td>
          <td>None</td>
          <td>-7,931,370,000,000.0</td>
          <td>-13,899,191,000,000.0</td>
          <td>-11,934,586,000,000.0</td>
          <td>-17,580,451,000,000.0</td>
          <td>-12,729,387,000,000.0</td>
          <td>-9,459,073,000,000.0</td>
          <td>-8,193,044,000,000.0</td>
          <td>-5,833,896,000,000.0</td>
          <td>-4,931,290,000,000.0</td>
          <td>-6,801,601,000,000.0</td>
        </tr>
        <tr>
          <th>55</th>
          <td>dart_OtherComprehensiveIncomeLossAccumulatedAm...</td>
          <td>매각예정분류기타자본항목</td>
          <td>Other Comprehensive income/loss accumulated am...</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>매각예정분류기타자본항목</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>-28,810,000,000.0</td>
          <td>23,797,000,000.0</td>
          <td>80,101,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>56</th>
          <td>ifrs_NoncontrollingInterests</td>
          <td>비지배지분</td>
          <td>Non-controlling interests</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>비지배지분</td>
          <td>None</td>
          <td>None</td>
          <td>7,684,184,000,000.0</td>
          <td>7,278,012,000,000.0</td>
          <td>6,538,705,000,000.0</td>
          <td>6,183,038,000,000.0</td>
          <td>5,906,463,000,000.0</td>
          <td>5,573,394,000,000.0</td>
          <td>4,386,154,000,000.0</td>
          <td>4,223,247,000,000.0</td>
          <td>3,736,075,000,000.0</td>
          <td>3,480,149,000,000.0</td>
        </tr>
        <tr>
          <th>57</th>
          <td>ifrs_Equity</td>
          <td>자본총계</td>
          <td>Total equity</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>자본총계</td>
          <td>None</td>
          <td>None</td>
          <td>247,753,177,000,000.0</td>
          <td>214,491,428,000,000.0</td>
          <td>192,963,033,000,000.0</td>
          <td>179,059,805,000,000.0</td>
          <td>168,088,188,000,000.0</td>
          <td>150,016,010,000,000.0</td>
          <td>121,480,206,000,000.0</td>
          <td>101,313,630,000,000.0</td>
          <td>89,177,636,000,000.0</td>
          <td>73,045,202,000,000.0</td>
        </tr>
        <tr>
          <th>58</th>
          <td>ifrs_EquityAndLiabilities</td>
          <td>자본과부채총계</td>
          <td>Total equity and liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>자본과부채총계</td>
          <td>None</td>
          <td>None</td>
          <td>None</td>
          <td>339,357,244,000,000.0</td>
          <td>301,752,090,000,000.0</td>
          <td>262,174,324,000,000.0</td>
          <td>242,179,521,000,000.0</td>
          <td>230,422,958,000,000.0</td>
          <td>214,075,018,000,000.0</td>
          <td>181,071,570,000,000.0</td>
          <td>155,800,263,000,000.0</td>
          <td>134,308,803,000,000.0</td>
          <td>112,179,789,000,000.0</td>
        </tr>
      </tbody>
    </table>
    </div>



4.2 연결 재무상태표(show\_depth 옵션)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: ipython3

    samsung_electronics.get_financial_statement(start_dt='20120101', show_depth=3)


.. parsed-literal::

    Loading report - annual: 100%|██████████| 7/7 [00:07<00:00,  1.16s/page]
    



.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>concept_id</th>
          <th>label_ko</th>
          <th>label_en</th>
          <th>class0</th>
          <th>class1</th>
          <th>class2</th>
          <th>[2018-12-31]연결재무제표</th>
          <th>[2017-12-31]연결재무제표</th>
          <th>[2016-12-31]연결재무제표</th>
          <th>[2015-12-31]연결재무제표</th>
          <th>[2014-12-31]연결재무제표</th>
          <th>[2013-12-31]연결재무제표</th>
          <th>[2012-12-31]연결재무제표</th>
          <th>[2011-12-31]연결재무제표</th>
          <th>[2010-12-31]연결재무제표</th>
          <th>[2009-12-31]연결재무제표</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>ifrs_CurrentAssets</td>
          <td>유동자산</td>
          <td>Current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>174,697,424,000,000.0</td>
          <td>146,982,464,000,000.0</td>
          <td>141,429,704,000,000.0</td>
          <td>124,814,725,000,000.0</td>
          <td>115,146,026,000,000.0</td>
          <td>110,760,271,000,000.0</td>
          <td>87,269,017,000,000.0</td>
          <td>71,502,063,000,000.0</td>
          <td>61,402,589,000,000.0</td>
          <td>54,211,297,000,000.0</td>
        </tr>
        <tr>
          <th>1</th>
          <td>ifrs_NoncurrentAssets</td>
          <td>비유동자산</td>
          <td>Non-current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>164,659,820,000,000.0</td>
          <td>154,769,626,000,000.0</td>
          <td>120,744,620,000,000.0</td>
          <td>117,364,796,000,000.0</td>
          <td>115,276,932,000,000.0</td>
          <td>103,314,747,000,000.0</td>
          <td>93,802,553,000,000.0</td>
          <td>84,298,200,000,000.0</td>
          <td>72,906,214,000,000.0</td>
          <td>57,968,492,000,000.0</td>
        </tr>
        <tr>
          <th>2</th>
          <td>ifrs_Assets</td>
          <td>자산총계</td>
          <td>Total assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>자산총계</td>
          <td>339,357,244,000,000.0</td>
          <td>301,752,090,000,000.0</td>
          <td>262,174,324,000,000.0</td>
          <td>242,179,521,000,000.0</td>
          <td>230,422,958,000,000.0</td>
          <td>214,075,018,000,000.0</td>
          <td>181,071,570,000,000.0</td>
          <td>155,800,263,000,000.0</td>
          <td>134,308,803,000,000.0</td>
          <td>112,179,789,000,000.0</td>
        </tr>
        <tr>
          <th>3</th>
          <td>ifrs_CurrentLiabilities</td>
          <td>유동부채</td>
          <td>Current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>69,081,510,000,000.0</td>
          <td>67,175,114,000,000.0</td>
          <td>54,704,095,000,000.0</td>
          <td>50,502,909,000,000.0</td>
          <td>52,013,913,000,000.0</td>
          <td>51,315,409,000,000.0</td>
          <td>46,933,052,000,000.0</td>
          <td>44,319,014,000,000.0</td>
          <td>39,944,721,000,000.0</td>
          <td>34,204,424,000,000.0</td>
        </tr>
        <tr>
          <th>4</th>
          <td>ifrs_NoncurrentLiabilities</td>
          <td>비유동부채</td>
          <td>Non-current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>22,522,557,000,000.0</td>
          <td>20,085,548,000,000.0</td>
          <td>14,507,196,000,000.0</td>
          <td>12,616,807,000,000.0</td>
          <td>10,320,857,000,000.0</td>
          <td>12,743,599,000,000.0</td>
          <td>12,658,312,000,000.0</td>
          <td>10,167,619,000,000.0</td>
          <td>5,186,446,000,000.0</td>
          <td>4,930,163,000,000.0</td>
        </tr>
        <tr>
          <th>5</th>
          <td>ifrs_Liabilities</td>
          <td>부채총계</td>
          <td>Total liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>부채총계</td>
          <td>91,604,067,000,000.0</td>
          <td>87,260,662,000,000.0</td>
          <td>69,211,291,000,000.0</td>
          <td>63,119,716,000,000.0</td>
          <td>62,334,770,000,000.0</td>
          <td>64,059,008,000,000.0</td>
          <td>59,591,364,000,000.0</td>
          <td>54,486,633,000,000.0</td>
          <td>45,131,167,000,000.0</td>
          <td>39,134,587,000,000.0</td>
        </tr>
        <tr>
          <th>6</th>
          <td>ifrs_EquityAttributableToOwnersOfParent</td>
          <td>지배기업 소유주지분</td>
          <td>Equity attributable to owners of parent</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>240,068,993,000,000.0</td>
          <td>207,213,416,000,000.0</td>
          <td>186,424,328,000,000.0</td>
          <td>172,876,767,000,000.0</td>
          <td>162,181,725,000,000.0</td>
          <td>144,442,616,000,000.0</td>
          <td>117,094,052,000,000.0</td>
          <td>97,090,383,000,000.0</td>
          <td>85,441,561,000,000.0</td>
          <td>69,565,053,000,000.0</td>
        </tr>
        <tr>
          <th>7</th>
          <td>ifrs_NoncontrollingInterests</td>
          <td>비지배지분</td>
          <td>Non-controlling interests</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>비지배지분</td>
          <td>7,684,184,000,000.0</td>
          <td>7,278,012,000,000.0</td>
          <td>6,538,705,000,000.0</td>
          <td>6,183,038,000,000.0</td>
          <td>5,906,463,000,000.0</td>
          <td>5,573,394,000,000.0</td>
          <td>4,386,154,000,000.0</td>
          <td>4,223,247,000,000.0</td>
          <td>3,736,075,000,000.0</td>
          <td>3,480,149,000,000.0</td>
        </tr>
        <tr>
          <th>8</th>
          <td>ifrs_Equity</td>
          <td>자본총계</td>
          <td>Total equity</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>자본총계</td>
          <td>247,753,177,000,000.0</td>
          <td>214,491,428,000,000.0</td>
          <td>192,963,033,000,000.0</td>
          <td>179,059,805,000,000.0</td>
          <td>168,088,188,000,000.0</td>
          <td>150,016,010,000,000.0</td>
          <td>121,480,206,000,000.0</td>
          <td>101,313,630,000,000.0</td>
          <td>89,177,636,000,000.0</td>
          <td>73,045,202,000,000.0</td>
        </tr>
        <tr>
          <th>9</th>
          <td>ifrs_EquityAndLiabilities</td>
          <td>자본과부채총계</td>
          <td>Total equity and liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>자본과부채총계</td>
          <td>None</td>
          <td>339,357,244,000,000.0</td>
          <td>301,752,090,000,000.0</td>
          <td>262,174,324,000,000.0</td>
          <td>242,179,521,000,000.0</td>
          <td>230,422,958,000,000.0</td>
          <td>214,075,018,000,000.0</td>
          <td>181,071,570,000,000.0</td>
          <td>155,800,263,000,000.0</td>
          <td>134,308,803,000,000.0</td>
          <td>112,179,789,000,000.0</td>
        </tr>
      </tbody>
    </table>
    </div>



4.3 개별 재무상태표(show\_depth: True)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: ipython3

    samsung_electronics.get_financial_statement(start_dt='20120101', separate=True, show_concept=False)


.. parsed-literal::

    Loading report - annual: 100%|██████████| 7/7 [00:06<00:00,  1.03s/page]
    



.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>label_ko</th>
          <th>label_en</th>
          <th>class0</th>
          <th>class1</th>
          <th>class2</th>
          <th>class3</th>
          <th>[2018-12-31]별도재무제표</th>
          <th>[2017-12-31]별도재무제표</th>
          <th>[2016-12-31]별도재무제표</th>
          <th>[2015-12-31]별도재무제표</th>
          <th>[2014-12-31]별도재무제표</th>
          <th>[2013-12-31]별도재무제표</th>
          <th>[2012-12-31]별도재무제표</th>
          <th>[2011-12-31]별도재무제표</th>
          <th>[2010-12-31]별도재무제표</th>
          <th>[2009-12-31]별도재무제표</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>유동자산</td>
          <td>Current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>None</td>
          <td>80,039,455,000,000.0</td>
          <td>70,155,189,000,000.0</td>
          <td>69,981,128,000,000.0</td>
          <td>67,002,055,000,000.0</td>
          <td>62,054,773,000,000.0</td>
          <td>60,603,694,000,000.0</td>
          <td>43,952,271,000,000.0</td>
          <td>39,496,344,000,000.0</td>
          <td>36,243,130,000,000.0</td>
          <td>29,898,907,000,000.0</td>
        </tr>
        <tr>
          <th>1</th>
          <td>현금및현금성자산</td>
          <td>Cash and cash equivalents</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>현금및현금성자산</td>
          <td>2,607,957,000,000.0</td>
          <td>2,763,768,000,000.0</td>
          <td>3,778,371,000,000.0</td>
          <td>3,062,960,000,000.0</td>
          <td>1,643,318,000,000.0</td>
          <td>2,030,307,000,000.0</td>
          <td>2,269,422,000,000.0</td>
          <td>2,718,731,000,000.0</td>
          <td>1,826,362,000,000.0</td>
          <td>2,142,220,000,000.0</td>
        </tr>
        <tr>
          <th>2</th>
          <td>단기금융상품</td>
          <td>Short-term financial instruments</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>단기금융상품</td>
          <td>34,113,871,000,000.0</td>
          <td>25,510,064,000,000.0</td>
          <td>30,170,656,000,000.0</td>
          <td>27,763,589,000,000.0</td>
          <td>26,454,093,000,000.0</td>
          <td>27,463,345,000,000.0</td>
          <td>13,400,572,000,000.0</td>
          <td>11,269,481,000,000.0</td>
          <td>10,930,660,000,000.0</td>
          <td>8,196,850,000,000.0</td>
        </tr>
        <tr>
          <th>3</th>
          <td>매출채권</td>
          <td>Short-term trade Receivable</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>매출채권</td>
          <td>24,933,267,000,000.0</td>
          <td>27,881,777,000,000.0</td>
          <td>23,514,012,000,000.0</td>
          <td>20,251,464,000,000.0</td>
          <td>18,940,786,000,000.0</td>
          <td>17,748,978,000,000.0</td>
          <td>17,296,647,000,000.0</td>
          <td>15,216,204,000,000.0</td>
          <td>13,377,718,000,000.0</td>
          <td>9,871,011,000,000.0</td>
        </tr>
        <tr>
          <th>4</th>
          <td>미수금</td>
          <td>Short-term other Receivables</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>미수금</td>
          <td>1,515,079,000,000.0</td>
          <td>2,201,402,000,000.0</td>
          <td>2,319,782,000,000.0</td>
          <td>2,314,823,000,000.0</td>
          <td>3,218,973,000,000.0</td>
          <td>2,734,572,000,000.0</td>
          <td>1,757,644,000,000.0</td>
          <td>1,580,639,000,000.0</td>
          <td>1,609,158,000,000.0</td>
          <td>1,386,975,000,000.0</td>
        </tr>
        <tr>
          <th>5</th>
          <td>선급금</td>
          <td>Advance paid</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>선급금</td>
          <td>807,262,000,000.0</td>
          <td>1,097,598,000,000.0</td>
          <td>814,300,000,000.0</td>
          <td>1,105,216,000,000.0</td>
          <td>977,114,000,000.0</td>
          <td>1,007,685,000,000.0</td>
          <td>883,859,000,000.0</td>
          <td>958,714,000,000.0</td>
          <td>904,550,000,000.0</td>
          <td>1,332,339,000,000.0</td>
        </tr>
        <tr>
          <th>6</th>
          <td>선급비용</td>
          <td>Prepaid expenses</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>선급비용</td>
          <td>2,230,628,000,000.0</td>
          <td>2,281,179,000,000.0</td>
          <td>2,375,520,000,000.0</td>
          <td>1,980,305,000,000.0</td>
          <td>1,846,360,000,000.0</td>
          <td>1,373,140,000,000.0</td>
          <td>1,091,766,000,000.0</td>
          <td>1,121,674,000,000.0</td>
          <td>1,097,422,000,000.0</td>
          <td>771,909,000,000.0</td>
        </tr>
        <tr>
          <th>7</th>
          <td>재고자산</td>
          <td>Inventories</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>재고자산</td>
          <td>12,440,951,000,000.0</td>
          <td>7,837,144,000,000.0</td>
          <td>5,981,634,000,000.0</td>
          <td>6,578,112,000,000.0</td>
          <td>5,553,834,000,000.0</td>
          <td>5,880,463,000,000.0</td>
          <td>5,326,417,000,000.0</td>
          <td>5,451,432,000,000.0</td>
          <td>4,750,964,000,000.0</td>
          <td>3,633,628,000,000.0</td>
        </tr>
        <tr>
          <th>8</th>
          <td>기타유동자산</td>
          <td>Other current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>기타유동자산</td>
          <td>1,390,440,000,000.0</td>
          <td>582,257,000,000.0</td>
          <td>743,163,000,000.0</td>
          <td>847,303,000,000.0</td>
          <td>821,079,000,000.0</td>
          <td>876,677,000,000.0</td>
          <td>667,071,000,000.0</td>
          <td>523,500,000,000.0</td>
          <td>587,152,000,000.0</td>
          <td>459,555,000,000.0</td>
        </tr>
        <tr>
          <th>9</th>
          <td>매각예정분류자산</td>
          <td>Non-current assets or disposal groups classifi...</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>매각예정분류자산</td>
          <td>nan</td>
          <td>nan</td>
          <td>283,690,000,000.0</td>
          <td>77,073,000,000.0</td>
          <td>461,683,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>10</th>
          <td>비유동자산</td>
          <td>Non-current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>None</td>
          <td>138,981,902,000,000.0</td>
          <td>128,086,171,000,000.0</td>
          <td>104,821,831,000,000.0</td>
          <td>101,967,575,000,000.0</td>
          <td>102,005,810,000,000.0</td>
          <td>94,222,263,000,000.0</td>
          <td>89,311,784,000,000.0</td>
          <td>78,103,505,000,000.0</td>
          <td>70,935,875,000,000.0</td>
          <td>59,710,447,000,000.0</td>
        </tr>
        <tr>
          <th>11</th>
          <td>장기매도가능금융자산</td>
          <td>Long-term deposits not classified as cash equi...</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>장기매도가능금융자산</td>
          <td>nan</td>
          <td>973,353,000,000.0</td>
          <td>913,989,000,000.0</td>
          <td>3,205,283,000,000.0</td>
          <td>7,106,234,000,000.0</td>
          <td>3,956,952,000,000.0</td>
          <td>3,618,727,000,000.0</td>
          <td>2,969,023,000,000.0</td>
          <td>2,690,819,000,000.0</td>
          <td>1,308,675,000,000.0</td>
        </tr>
        <tr>
          <th>12</th>
          <td>기타포괄손익-공정가치금융자산</td>
          <td>fair value capital asset-oci</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>기타포괄손익-공정가치금융자산</td>
          <td>1,098,565,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>13</th>
          <td>당기손익-공정가치금융자산</td>
          <td>fair value capital asset-income</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>당기손익-공정가치금융자산</td>
          <td>7,413,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>14</th>
          <td>종속기업, 관계기업 및 공동기업 투자</td>
          <td>Investments in subsidiaries, joint ventures an...</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>종속기업, 관계기업 및 공동기업 투자</td>
          <td>55,959,745,000,000.0</td>
          <td>55,671,759,000,000.0</td>
          <td>48,743,079,000,000.0</td>
          <td>44,107,398,000,000.0</td>
          <td>41,857,431,000,000.0</td>
          <td>42,258,049,000,000.0</td>
          <td>39,478,292,000,000.0</td>
          <td>25,464,768,000,000.0</td>
          <td>22,631,419,000,000.0</td>
          <td>22,046,679,000,000.0</td>
        </tr>
        <tr>
          <th>15</th>
          <td>유형자산</td>
          <td>Property, plant and equipment</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>유형자산</td>
          <td>70,602,493,000,000.0</td>
          <td>62,816,961,000,000.0</td>
          <td>47,228,830,000,000.0</td>
          <td>45,148,629,000,000.0</td>
          <td>43,744,259,000,000.0</td>
          <td>41,439,372,000,000.0</td>
          <td>39,808,935,000,000.0</td>
          <td>43,032,531,000,000.0</td>
          <td>38,708,906,000,000.0</td>
          <td>32,306,828,000,000.0</td>
        </tr>
        <tr>
          <th>16</th>
          <td>무형자산</td>
          <td>Investment property</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>무형자산</td>
          <td>2,901,476,000,000.0</td>
          <td>2,827,035,000,000.0</td>
          <td>2,891,844,000,000.0</td>
          <td>3,407,229,000,000.0</td>
          <td>3,051,564,000,000.0</td>
          <td>2,495,302,000,000.0</td>
          <td>2,464,948,000,000.0</td>
          <td>2,447,791,000,000.0</td>
          <td>2,439,491,000,000.0</td>
          <td>1,020,209,000,000.0</td>
        </tr>
        <tr>
          <th>17</th>
          <td>장기선급비용</td>
          <td>Long-term prepaid expenses</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>장기선급비용</td>
          <td>4,108,410,000,000.0</td>
          <td>3,031,327,000,000.0</td>
          <td>3,507,399,000,000.0</td>
          <td>3,845,119,000,000.0</td>
          <td>4,415,935,000,000.0</td>
          <td>2,951,813,000,000.0</td>
          <td>2,924,694,000,000.0</td>
          <td>3,048,948,000,000.0</td>
          <td>3,411,517,000,000.0</td>
          <td>2,342,921,000,000.0</td>
        </tr>
        <tr>
          <th>18</th>
          <td>순확정급여자산</td>
          <td>Deposits for severance insurance</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>순확정급여자산</td>
          <td>562,356,000,000.0</td>
          <td>811,210,000,000.0</td>
          <td>557,091,000,000.0</td>
          <td>56,174,000,000.0</td>
          <td>135,951,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>19</th>
          <td>이연법인세자산</td>
          <td>Deferred tax assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>이연법인세자산</td>
          <td>654,456,000,000.0</td>
          <td>586,161,000,000.0</td>
          <td>110,239,000,000.0</td>
          <td>865,903,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>142,314,000,000.0</td>
          <td>202,158,000,000.0</td>
          <td>0.0</td>
          <td>0.0</td>
        </tr>
        <tr>
          <th>20</th>
          <td>기타비유동자산</td>
          <td>Other non-current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>기타비유동자산</td>
          <td>3,086,988,000,000.0</td>
          <td>1,368,365,000,000.0</td>
          <td>869,360,000,000.0</td>
          <td>1,331,840,000,000.0</td>
          <td>1,694,436,000,000.0</td>
          <td>1,120,775,000,000.0</td>
          <td>873,874,000,000.0</td>
          <td>938,286,000,000.0</td>
          <td>772,844,000,000.0</td>
          <td>428,632,000,000.0</td>
        </tr>
        <tr>
          <th>21</th>
          <td>자산총계</td>
          <td>Total assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>자산총계</td>
          <td>None</td>
          <td>219,021,357,000,000.0</td>
          <td>198,241,360,000,000.0</td>
          <td>174,802,959,000,000.0</td>
          <td>168,969,630,000,000.0</td>
          <td>164,060,583,000,000.0</td>
          <td>154,825,957,000,000.0</td>
          <td>133,264,055,000,000.0</td>
          <td>117,599,849,000,000.0</td>
          <td>107,179,005,000,000.0</td>
          <td>89,609,354,000,000.0</td>
        </tr>
        <tr>
          <th>22</th>
          <td>유동부채</td>
          <td>Current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>None</td>
          <td>43,145,053,000,000.0</td>
          <td>44,495,084,000,000.0</td>
          <td>34,076,122,000,000.0</td>
          <td>29,630,488,000,000.0</td>
          <td>28,208,638,000,000.0</td>
          <td>27,597,944,000,000.0</td>
          <td>24,770,263,000,000.0</td>
          <td>26,969,912,000,000.0</td>
          <td>24,991,737,000,000.0</td>
          <td>20,304,724,000,000.0</td>
        </tr>
        <tr>
          <th>23</th>
          <td>매입채무</td>
          <td>Trade account payable</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>매입채무</td>
          <td>7,315,631,000,000.0</td>
          <td>6,398,629,000,000.0</td>
          <td>6,162,650,000,000.0</td>
          <td>3,887,983,000,000.0</td>
          <td>4,677,527,000,000.0</td>
          <td>5,742,116,000,000.0</td>
          <td>5,785,104,000,000.0</td>
          <td>6,983,494,000,000.0</td>
          <td>6,022,488,000,000.0</td>
          <td>4,785,268,000,000.0</td>
        </tr>
        <tr>
          <th>24</th>
          <td>단기차입금</td>
          <td>Short-term borrowings</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>단기차입금</td>
          <td>10,353,873,000,000.0</td>
          <td>12,229,701,000,000.0</td>
          <td>9,061,167,000,000.0</td>
          <td>7,127,527,000,000.0</td>
          <td>2,928,182,000,000.0</td>
          <td>2,811,565,000,000.0</td>
          <td>3,034,621,000,000.0</td>
          <td>4,259,170,000,000.0</td>
          <td>4,415,095,000,000.0</td>
          <td>3,579,760,000,000.0</td>
        </tr>
        <tr>
          <th>25</th>
          <td>미지급금</td>
          <td>Other payable</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>미지급금</td>
          <td>8,385,752,000,000.0</td>
          <td>9,598,654,000,000.0</td>
          <td>7,635,740,000,000.0</td>
          <td>5,952,236,000,000.0</td>
          <td>6,460,166,000,000.0</td>
          <td>5,404,573,000,000.0</td>
          <td>4,423,468,000,000.0</td>
          <td>6,509,234,000,000.0</td>
          <td>5,893,021,000,000.0</td>
          <td>4,595,940,000,000.0</td>
        </tr>
        <tr>
          <th>26</th>
          <td>선수금</td>
          <td>Advance received</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>선수금</td>
          <td>214,615,000,000.0</td>
          <td>214,007,000,000.0</td>
          <td>200,445,000,000.0</td>
          <td>160,990,000,000.0</td>
          <td>139,803,000,000.0</td>
          <td>141,582,000,000.0</td>
          <td>218,229,000,000.0</td>
          <td>979,418,000,000.0</td>
          <td>588,206,000,000.0</td>
          <td>700,733,000,000.0</td>
        </tr>
        <tr>
          <th>27</th>
          <td>예수금</td>
          <td>Withholdings</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>예수금</td>
          <td>572,702,000,000.0</td>
          <td>500,740,000,000.0</td>
          <td>389,528,000,000.0</td>
          <td>341,806,000,000.0</td>
          <td>596,164,000,000.0</td>
          <td>514,235,000,000.0</td>
          <td>459,481,000,000.0</td>
          <td>574,015,000,000.0</td>
          <td>315,196,000,000.0</td>
          <td>275,994,000,000.0</td>
        </tr>
        <tr>
          <th>28</th>
          <td>미지급비용</td>
          <td>Accrued expenses</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>미지급비용</td>
          <td>6,129,837,000,000.0</td>
          <td>6,657,674,000,000.0</td>
          <td>6,284,646,000,000.0</td>
          <td>6,126,350,000,000.0</td>
          <td>7,413,148,000,000.0</td>
          <td>5,952,745,000,000.0</td>
          <td>5,469,762,000,000.0</td>
          <td>5,027,821,000,000.0</td>
          <td>4,444,795,000,000.0</td>
          <td>3,811,656,000,000.0</td>
        </tr>
        <tr>
          <th>29</th>
          <td>미지급법인세</td>
          <td>Payments of income taxes payable</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>미지급법인세</td>
          <td>7,925,887,000,000.0</td>
          <td>6,565,781,000,000.0</td>
          <td>2,055,829,000,000.0</td>
          <td>1,802,344,000,000.0</td>
          <td>1,707,176,000,000.0</td>
          <td>2,207,118,000,000.0</td>
          <td>2,217,161,000,000.0</td>
          <td>614,256,000,000.0</td>
          <td>1,713,443,000,000.0</td>
          <td>625,898,000,000.0</td>
        </tr>
        <tr>
          <th>30</th>
          <td>유동성장기부채</td>
          <td>Current portion of long-term borrowings and de...</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>유동성장기부채</td>
          <td>5,440,000,000.0</td>
          <td>5,201,000,000.0</td>
          <td>5,854,000,000.0</td>
          <td>5,666,000,000.0</td>
          <td>5,304,000,000.0</td>
          <td>5,083,000,000.0</td>
          <td>5,150,000,000.0</td>
          <td>5,536,000,000.0</td>
          <td>5,459,000,000.0</td>
          <td>5,588,000,000.0</td>
        </tr>
        <tr>
          <th>31</th>
          <td>충당부채</td>
          <td>Current provisions</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>충당부채</td>
          <td>2,135,314,000,000.0</td>
          <td>2,273,688,000,000.0</td>
          <td>2,221,717,000,000.0</td>
          <td>4,207,745,000,000.0</td>
          <td>4,246,054,000,000.0</td>
          <td>4,805,193,000,000.0</td>
          <td>3,134,268,000,000.0</td>
          <td>1,858,861,000,000.0</td>
          <td>1,326,152,000,000.0</td>
          <td>1,604,335,000,000.0</td>
        </tr>
        <tr>
          <th>32</th>
          <td>기타유동부채</td>
          <td>Other current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>기타유동부채</td>
          <td>106,002,000,000.0</td>
          <td>51,009,000,000.0</td>
          <td>58,546,000,000.0</td>
          <td>17,841,000,000.0</td>
          <td>14,855,000,000.0</td>
          <td>13,734,000,000.0</td>
          <td>23,019,000,000.0</td>
          <td>158,107,000,000.0</td>
          <td>267,882,000,000.0</td>
          <td>319,552,000,000.0</td>
        </tr>
        <tr>
          <th>33</th>
          <td>비유동부채</td>
          <td>Non-current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>None</td>
          <td>2,888,179,000,000.0</td>
          <td>2,176,501,000,000.0</td>
          <td>3,180,075,000,000.0</td>
          <td>2,910,887,000,000.0</td>
          <td>3,174,870,000,000.0</td>
          <td>4,857,246,000,000.0</td>
          <td>2,605,923,000,000.0</td>
          <td>2,173,031,000,000.0</td>
          <td>2,327,044,000,000.0</td>
          <td>2,550,164,000,000.0</td>
        </tr>
        <tr>
          <th>34</th>
          <td>사채</td>
          <td>Bonds issued</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>사채</td>
          <td>43,516,000,000.0</td>
          <td>46,808,000,000.0</td>
          <td>58,542,000,000.0</td>
          <td>62,326,000,000.0</td>
          <td>63,648,000,000.0</td>
          <td>66,079,000,000.0</td>
          <td>72,103,000,000.0</td>
          <td>83,045,000,000.0</td>
          <td>87,338,000,000.0</td>
          <td>94,993,000,000.0</td>
        </tr>
        <tr>
          <th>35</th>
          <td>장기미지급금</td>
          <td>Long-Term other Payables, gross</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>장기미지급금</td>
          <td>2,472,416,000,000.0</td>
          <td>1,750,379,000,000.0</td>
          <td>2,808,460,000,000.0</td>
          <td>2,387,934,000,000.0</td>
          <td>2,305,055,000,000.0</td>
          <td>769,002,000,000.0</td>
          <td>775,585,000,000.0</td>
          <td>697,705,000,000.0</td>
          <td>870,180,000,000.0</td>
          <td>900,648,000,000.0</td>
        </tr>
        <tr>
          <th>36</th>
          <td>장기충당부채</td>
          <td>Long-term trade and other non-current payables</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>장기충당부채</td>
          <td>372,217,000,000.0</td>
          <td>379,201,000,000.0</td>
          <td>312,467,000,000.0</td>
          <td>457,290,000,000.0</td>
          <td>437,974,000,000.0</td>
          <td>415,718,000,000.0</td>
          <td>367,743,000,000.0</td>
          <td>351,556,000,000.0</td>
          <td>295,356,000,000.0</td>
          <td>244,443,000,000.0</td>
        </tr>
        <tr>
          <th>37</th>
          <td>기타비유동부채</td>
          <td>Other non-current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>기타비유동부채</td>
          <td>30,000,000.0</td>
          <td>113,000,000.0</td>
          <td>606,000,000.0</td>
          <td>3,337,000,000.0</td>
          <td>3,827,000,000.0</td>
          <td>152,054,000,000.0</td>
          <td>12,387,000,000.0</td>
          <td>175,797,000,000.0</td>
          <td>166,291,000,000.0</td>
          <td>202,918,000,000.0</td>
        </tr>
        <tr>
          <th>38</th>
          <td>부채총계</td>
          <td>Total liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>부채총계</td>
          <td>None</td>
          <td>46,033,232,000,000.0</td>
          <td>46,671,585,000,000.0</td>
          <td>37,256,197,000,000.0</td>
          <td>32,541,375,000,000.0</td>
          <td>31,383,508,000,000.0</td>
          <td>32,455,190,000,000.0</td>
          <td>27,376,186,000,000.0</td>
          <td>29,142,943,000,000.0</td>
          <td>27,318,781,000,000.0</td>
          <td>22,854,888,000,000.0</td>
        </tr>
        <tr>
          <th>39</th>
          <td>자본금</td>
          <td>Issued capital</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>자본금</td>
          <td>None</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
        </tr>
        <tr>
          <th>40</th>
          <td>우선주자본금</td>
          <td>Issued capital of preferred stock</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>자본금</td>
          <td>우선주자본금</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
        </tr>
        <tr>
          <th>41</th>
          <td>보통주자본금</td>
          <td>Issued capital of common stock</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>자본금</td>
          <td>보통주자본금</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
        </tr>
        <tr>
          <th>42</th>
          <td>주식발행초과금</td>
          <td>Share premium</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>주식발행초과금</td>
          <td>None</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
        </tr>
        <tr>
          <th>43</th>
          <td>이익잉여금</td>
          <td>Retained earnings</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>이익잉여금</td>
          <td>None</td>
          <td>166,555,532,000,000.0</td>
          <td>150,928,724,000,000.0</td>
          <td>140,747,574,000,000.0</td>
          <td>143,629,177,000,000.0</td>
          <td>134,464,189,000,000.0</td>
          <td>122,029,419,000,000.0</td>
          <td>105,306,520,000,000.0</td>
          <td>88,735,491,000,000.0</td>
          <td>79,511,777,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>44</th>
          <td>기타자본항목</td>
          <td>Elements of other stockholder's equity</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>기타자본항목</td>
          <td>None</td>
          <td>1,131,186,000,000.0</td>
          <td>-4,660,356,000,000.0</td>
          <td>-8,502,219,000,000.0</td>
          <td>-12,526,126,000,000.0</td>
          <td>-7,113,271,000,000.0</td>
          <td>-4,960,059,000,000.0</td>
          <td>-4,720,058,000,000.0</td>
          <td>-5,579,992,000,000.0</td>
          <td>-4,952,960,000,000.0</td>
          <td>-6,632,299,000,000.0</td>
        </tr>
        <tr>
          <th>45</th>
          <td>자본총계</td>
          <td>Total equity</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>자본총계</td>
          <td>None</td>
          <td>172,988,125,000,000.0</td>
          <td>151,569,775,000,000.0</td>
          <td>137,546,762,000,000.0</td>
          <td>136,428,255,000,000.0</td>
          <td>132,677,075,000,000.0</td>
          <td>122,370,767,000,000.0</td>
          <td>105,887,869,000,000.0</td>
          <td>88,456,906,000,000.0</td>
          <td>79,860,224,000,000.0</td>
          <td>66,754,466,000,000.0</td>
        </tr>
        <tr>
          <th>46</th>
          <td>자본과부채총계</td>
          <td>Total equity and liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>자본과부채총계</td>
          <td>None</td>
          <td>None</td>
          <td>219,021,357,000,000.0</td>
          <td>198,241,360,000,000.0</td>
          <td>174,802,959,000,000.0</td>
          <td>168,969,630,000,000.0</td>
          <td>164,060,583,000,000.0</td>
          <td>154,825,957,000,000.0</td>
          <td>133,264,055,000,000.0</td>
          <td>117,599,849,000,000.0</td>
          <td>107,179,005,000,000.0</td>
          <td>89,609,354,000,000.0</td>
        </tr>
      </tbody>
    </table>
    </div>



4.4 연결 재무상태표(반기 및 분기 포함)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: ipython3

    samsung_electronics.get_financial_statement(start_dt='20160101', report_tp='quarter')


.. parsed-literal::

    Download: 31.0KB [00:00, 200KB/s]
    Loading report - annual: 100%|██████████| 3/3 [00:02<00:00,  1.01page/s]
    Loading report - half: 100%|██████████| 2/2 [00:01<00:00,  1.02page/s]
    Loading report - quarter: 100%|██████████| 5/5 [00:05<00:00,  1.01page/s]
    



.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>concept_id</th>
          <th>label_ko</th>
          <th>label_en</th>
          <th>class0</th>
          <th>class1</th>
          <th>class2</th>
          <th>class3</th>
          <th>class4</th>
          <th>[2018-12-31]연결재무제표</th>
          <th>[2018-09-30]연결재무제표</th>
          <th>...</th>
          <th>[2018-03-31]연결재무제표</th>
          <th>[2017-12-31]연결재무제표</th>
          <th>[2017-09-30]연결재무제표</th>
          <th>[2017-06-30]연결재무제표</th>
          <th>[2017-03-31]연결재무제표</th>
          <th>[2016-12-31]연결재무제표</th>
          <th>[2016-09-30]연결재무제표</th>
          <th>[2015-12-31]연결재무제표</th>
          <th>[2014-12-31]연결재무제표</th>
          <th>[2013-12-31]연결재무제표</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>ifrs_CurrentAssets</td>
          <td>유동자산</td>
          <td>Current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>None</td>
          <td>None</td>
          <td>174,697,424,000,000.0</td>
          <td>176,282,049,000,000.0</td>
          <td>...</td>
          <td>154,941,953,000,000.0</td>
          <td>146,982,464,000,000.0</td>
          <td>145,322,337,000,000.0</td>
          <td>132,172,681,000,000.0</td>
          <td>129,284,204,000,000.0</td>
          <td>141,429,704,000,000.0</td>
          <td>132,166,769,000,000.0</td>
          <td>124,814,725,000,000.0</td>
          <td>115,146,026,000,000.0</td>
          <td>110,760,271,000,000.0</td>
        </tr>
        <tr>
          <th>1</th>
          <td>ifrs_CashAndCashEquivalents</td>
          <td>현금및현금성자산</td>
          <td>Cash and cash equivalents</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>현금및현금성자산</td>
          <td>None</td>
          <td>30,340,505,000,000.0</td>
          <td>33,088,093,000,000.0</td>
          <td>...</td>
          <td>32,303,752,000,000.0</td>
          <td>30,545,130,000,000.0</td>
          <td>30,788,226,000,000.0</td>
          <td>29,007,086,000,000.0</td>
          <td>27,562,938,000,000.0</td>
          <td>32,111,442,000,000.0</td>
          <td>25,267,569,000,000.0</td>
          <td>22,636,744,000,000.0</td>
          <td>16,840,766,000,000.0</td>
          <td>16,284,780,000,000.0</td>
        </tr>
        <tr>
          <th>2</th>
          <td>dart_ShortTermDepositsNotClassifiedAsCashEquiv...</td>
          <td>단기금융상품</td>
          <td>Short-term financial instruments</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>단기금융상품</td>
          <td>None</td>
          <td>65,893,797,000,000.0</td>
          <td>58,681,418,000,000.0</td>
          <td>...</td>
          <td>46,027,700,000,000.0</td>
          <td>49,447,696,000,000.0</td>
          <td>41,280,668,000,000.0</td>
          <td>37,796,229,000,000.0</td>
          <td>41,775,404,000,000.0</td>
          <td>52,432,411,000,000.0</td>
          <td>53,247,062,000,000.0</td>
          <td>44,228,800,000,000.0</td>
          <td>41,689,776,000,000.0</td>
          <td>36,722,702,000,000.0</td>
        </tr>
        <tr>
          <th>3</th>
          <td>entity00126380_udf_BS_20171018214525642_Curren...</td>
          <td>단기매도가능금융자산</td>
          <td>Available-for-sale financial assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>단기매도가능금융자산</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>...</td>
          <td>nan</td>
          <td>3,191,375,000,000.0</td>
          <td>3,964,250,000,000.0</td>
          <td>3,698,772,000,000.0</td>
          <td>4,063,945,000,000.0</td>
          <td>3,638,460,000,000.0</td>
          <td>3,607,340,000,000.0</td>
          <td>4,627,530,000,000.0</td>
          <td>3,286,798,000,000.0</td>
          <td>1,488,527,000,000.0</td>
        </tr>
        <tr>
          <th>4</th>
          <td>entity00126380_udf_BS_201851017339116_CurrentA...</td>
          <td>단기상각후원가금융자산</td>
          <td>after depreciation capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>단기상각후원가금융자산</td>
          <td>None</td>
          <td>2,703,693,000,000.0</td>
          <td>3,446,114,000,000.0</td>
          <td>...</td>
          <td>3,733,160,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>5</th>
          <td>entity00126380_udf_BS_201931110524523_CurrentA...</td>
          <td>단기당기손익-공정가치금융자산</td>
          <td>income-fair value capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>단기당기손익-공정가치금융자산</td>
          <td>None</td>
          <td>2,001,948,000,000.0</td>
          <td>nan</td>
          <td>...</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>6</th>
          <td>dart_ShortTermTradeReceivable</td>
          <td>매출채권</td>
          <td>Short-term trade Receivable</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>매출채권</td>
          <td>None</td>
          <td>33,867,733,000,000.0</td>
          <td>41,940,008,000,000.0</td>
          <td>...</td>
          <td>35,370,654,000,000.0</td>
          <td>27,695,995,000,000.0</td>
          <td>30,351,245,000,000.0</td>
          <td>27,585,923,000,000.0</td>
          <td>22,340,688,000,000.0</td>
          <td>24,279,211,000,000.0</td>
          <td>21,693,242,000,000.0</td>
          <td>25,168,026,000,000.0</td>
          <td>24,694,610,000,000.0</td>
          <td>24,988,532,000,000.0</td>
        </tr>
        <tr>
          <th>7</th>
          <td>entity00126380_udf_BS_201710182279121_CurrentA...</td>
          <td>미수금</td>
          <td>Other account receivables</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>미수금</td>
          <td>None</td>
          <td>3,080,733,000,000.0</td>
          <td>3,155,484,000,000.0</td>
          <td>...</td>
          <td>3,221,846,000,000.0</td>
          <td>4,108,961,000,000.0</td>
          <td>3,551,281,000,000.0</td>
          <td>3,197,546,000,000.0</td>
          <td>3,557,039,000,000.0</td>
          <td>3,521,197,000,000.0</td>
          <td>2,659,273,000,000.0</td>
          <td>3,352,663,000,000.0</td>
          <td>3,539,875,000,000.0</td>
          <td>2,887,402,000,000.0</td>
        </tr>
        <tr>
          <th>8</th>
          <td>entity00126380_udf_BS_20171018221011173_Curren...</td>
          <td>선급금</td>
          <td>Advance payment</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>선급금</td>
          <td>None</td>
          <td>1,361,807,000,000.0</td>
          <td>1,473,652,000,000.0</td>
          <td>...</td>
          <td>1,687,013,000,000.0</td>
          <td>1,753,673,000,000.0</td>
          <td>1,960,054,000,000.0</td>
          <td>1,757,708,000,000.0</td>
          <td>1,662,898,000,000.0</td>
          <td>1,439,938,000,000.0</td>
          <td>1,513,284,000,000.0</td>
          <td>1,706,003,000,000.0</td>
          <td>1,989,470,000,000.0</td>
          <td>1,928,188,000,000.0</td>
        </tr>
        <tr>
          <th>9</th>
          <td>entity00126380_udf_BS_2017101822109437_Current...</td>
          <td>선급비용</td>
          <td>Prepaid expense</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>선급비용</td>
          <td>None</td>
          <td>4,136,167,000,000.0</td>
          <td>4,201,481,000,000.0</td>
          <td>...</td>
          <td>4,327,031,000,000.0</td>
          <td>3,835,219,000,000.0</td>
          <td>4,155,405,000,000.0</td>
          <td>3,705,124,000,000.0</td>
          <td>4,149,992,000,000.0</td>
          <td>3,502,083,000,000.0</td>
          <td>3,768,527,000,000.0</td>
          <td>3,170,632,000,000.0</td>
          <td>3,346,593,000,000.0</td>
          <td>2,472,950,000,000.0</td>
        </tr>
        <tr>
          <th>10</th>
          <td>ifrs_Inventories</td>
          <td>재고자산</td>
          <td>Inventories</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>재고자산</td>
          <td>None</td>
          <td>28,984,704,000,000.0</td>
          <td>28,242,807,000,000.0</td>
          <td>...</td>
          <td>26,470,871,000,000.0</td>
          <td>24,983,355,000,000.0</td>
          <td>27,032,501,000,000.0</td>
          <td>23,020,912,000,000.0</td>
          <td>21,857,598,000,000.0</td>
          <td>18,353,503,000,000.0</td>
          <td>18,378,245,000,000.0</td>
          <td>18,811,794,000,000.0</td>
          <td>17,317,504,000,000.0</td>
          <td>19,134,868,000,000.0</td>
        </tr>
        <tr>
          <th>11</th>
          <td>dart_OtherCurrentAssets</td>
          <td>기타유동자산</td>
          <td>Other current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>기타유동자산</td>
          <td>None</td>
          <td>2,326,337,000,000.0</td>
          <td>2,052,992,000,000.0</td>
          <td>...</td>
          <td>1,799,926,000,000.0</td>
          <td>1,421,060,000,000.0</td>
          <td>1,318,309,000,000.0</td>
          <td>1,521,698,000,000.0</td>
          <td>1,512,919,000,000.0</td>
          <td>1,315,653,000,000.0</td>
          <td>927,739,000,000.0</td>
          <td>1,035,460,000,000.0</td>
          <td>1,795,143,000,000.0</td>
          <td>2,135,589,000,000.0</td>
        </tr>
        <tr>
          <th>12</th>
          <td>ifrs_NoncurrentAssetsOrDisposalGroupsClassifie...</td>
          <td>매각예정분류자산</td>
          <td>Non-current assets or disposal groups classifi...</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>유동자산</td>
          <td>매각예정분류자산</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>...</td>
          <td>nan</td>
          <td>nan</td>
          <td>920,398,000,000.0</td>
          <td>881,683,000,000.0</td>
          <td>800,783,000,000.0</td>
          <td>835,806,000,000.0</td>
          <td>1,104,488,000,000.0</td>
          <td>77,073,000,000.0</td>
          <td>645,491,000,000.0</td>
          <td>2,716,733,000,000.0</td>
        </tr>
        <tr>
          <th>13</th>
          <td>ifrs_NoncurrentAssets</td>
          <td>비유동자산</td>
          <td>Non-current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>None</td>
          <td>None</td>
          <td>164,659,820,000,000.0</td>
          <td>160,913,737,000,000.0</td>
          <td>...</td>
          <td>157,531,160,000,000.0</td>
          <td>154,769,626,000,000.0</td>
          <td>151,256,242,000,000.0</td>
          <td>145,416,755,000,000.0</td>
          <td>134,933,168,000,000.0</td>
          <td>120,744,620,000,000.0</td>
          <td>112,304,687,000,000.0</td>
          <td>117,364,796,000,000.0</td>
          <td>115,276,932,000,000.0</td>
          <td>103,314,747,000,000.0</td>
        </tr>
        <tr>
          <th>14</th>
          <td>dart_LongTermDepositsNotClassifiedAsCashEquiva...</td>
          <td>장기매도가능금융자산</td>
          <td>Long-term deposits not classified as cash equi...</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>장기매도가능금융자산</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>...</td>
          <td>nan</td>
          <td>7,752,180,000,000.0</td>
          <td>8,066,146,000,000.0</td>
          <td>7,565,787,000,000.0</td>
          <td>6,967,149,000,000.0</td>
          <td>6,804,276,000,000.0</td>
          <td>7,681,238,000,000.0</td>
          <td>8,332,480,000,000.0</td>
          <td>12,667,509,000,000.0</td>
          <td>6,238,380,000,000.0</td>
        </tr>
        <tr>
          <th>15</th>
          <td>entity00126380_udf_BS_20182211113197_Noncurren...</td>
          <td>만기보유금융자산</td>
          <td>Held-to-maturity</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>만기보유금융자산</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>...</td>
          <td>nan</td>
          <td>106,751,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>16</th>
          <td>entity00126380_udf_BS_20185101782898_Noncurren...</td>
          <td>상각후원가금융자산</td>
          <td>after depreciation capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>상각후원가금융자산</td>
          <td>None</td>
          <td>238,309,000,000.0</td>
          <td>242,423,000,000.0</td>
          <td>...</td>
          <td>260,660,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>17</th>
          <td>entity00126380_udf_BS_201851017830322_Noncurre...</td>
          <td>기타포괄손익-공정가치금융자산</td>
          <td>oci-fair value capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>기타포괄손익-공정가치금융자산</td>
          <td>None</td>
          <td>7,301,351,000,000.0</td>
          <td>nan</td>
          <td>...</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>18</th>
          <td>entity00126380_udf_BS_201851017832579_Noncurre...</td>
          <td>당기손익-공정가치금융자산</td>
          <td>income-fair value capital asset</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>당기손익-공정가치금융자산</td>
          <td>None</td>
          <td>775,427,000,000.0</td>
          <td>nan</td>
          <td>...</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>19</th>
          <td>entity00126380_udf_BS_20171018221637438_Noncur...</td>
          <td>관계기업 및 공동기업 투자</td>
          <td>Availalble for sale financial asset associates...</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>관계기업 및 공동기업 투자</td>
          <td>None</td>
          <td>7,313,206,000,000.0</td>
          <td>7,005,344,000,000.0</td>
          <td>...</td>
          <td>6,810,645,000,000.0</td>
          <td>6,802,351,000,000.0</td>
          <td>5,914,258,000,000.0</td>
          <td>5,814,880,000,000.0</td>
          <td>5,701,362,000,000.0</td>
          <td>5,837,884,000,000.0</td>
          <td>3,721,673,000,000.0</td>
          <td>5,276,348,000,000.0</td>
          <td>5,232,461,000,000.0</td>
          <td>6,422,292,000,000.0</td>
        </tr>
        <tr>
          <th>20</th>
          <td>ifrs_PropertyPlantAndEquipment</td>
          <td>유형자산</td>
          <td>Property, plant and equipment</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>유형자산</td>
          <td>None</td>
          <td>115,416,724,000,000.0</td>
          <td>115,003,148,000,000.0</td>
          <td>...</td>
          <td>114,412,258,000,000.0</td>
          <td>111,665,648,000,000.0</td>
          <td>109,006,091,000,000.0</td>
          <td>103,695,240,000,000.0</td>
          <td>95,322,418,000,000.0</td>
          <td>91,473,041,000,000.0</td>
          <td>83,873,784,000,000.0</td>
          <td>86,477,110,000,000.0</td>
          <td>80,872,950,000,000.0</td>
          <td>75,496,388,000,000.0</td>
        </tr>
        <tr>
          <th>21</th>
          <td>ifrs_InvestmentProperty</td>
          <td>무형자산</td>
          <td>Investment property</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>무형자산</td>
          <td>None</td>
          <td>14,891,598,000,000.0</td>
          <td>14,800,096,000,000.0</td>
          <td>...</td>
          <td>14,805,407,000,000.0</td>
          <td>14,760,483,000,000.0</td>
          <td>15,376,169,000,000.0</td>
          <td>15,221,308,000,000.0</td>
          <td>14,775,930,000,000.0</td>
          <td>5,344,020,000,000.0</td>
          <td>5,088,233,000,000.0</td>
          <td>5,396,311,000,000.0</td>
          <td>4,785,473,000,000.0</td>
          <td>3,980,600,000,000.0</td>
        </tr>
        <tr>
          <th>22</th>
          <td>dart_LongTermPrepaidExpenses</td>
          <td>장기선급비용</td>
          <td>Long-term prepaid expenses</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>장기선급비용</td>
          <td>None</td>
          <td>5,009,679,000,000.0</td>
          <td>3,482,233,000,000.0</td>
          <td>...</td>
          <td>3,880,465,000,000.0</td>
          <td>3,434,375,000,000.0</td>
          <td>3,381,655,000,000.0</td>
          <td>3,200,623,000,000.0</td>
          <td>3,586,776,000,000.0</td>
          <td>3,834,831,000,000.0</td>
          <td>4,161,267,000,000.0</td>
          <td>4,294,401,000,000.0</td>
          <td>4,857,126,000,000.0</td>
          <td>3,465,783,000,000.0</td>
        </tr>
        <tr>
          <th>23</th>
          <td>dart_DepositsForSeveranceInsurance</td>
          <td>순확정급여자산</td>
          <td>Deposits for severance insurance</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>순확정급여자산</td>
          <td>None</td>
          <td>562,356,000,000.0</td>
          <td>289,962,000,000.0</td>
          <td>...</td>
          <td>628,122,000,000.0</td>
          <td>825,892,000,000.0</td>
          <td>120,688,000,000.0</td>
          <td>302,335,000,000.0</td>
          <td>469,696,000,000.0</td>
          <td>557,091,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>24</th>
          <td>ifrs_DeferredTaxAssets</td>
          <td>이연법인세자산</td>
          <td>Deferred tax assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>이연법인세자산</td>
          <td>None</td>
          <td>5,468,002,000,000.0</td>
          <td>4,692,581,000,000.0</td>
          <td>...</td>
          <td>5,012,377,000,000.0</td>
          <td>5,061,687,000,000.0</td>
          <td>5,026,790,000,000.0</td>
          <td>5,368,206,000,000.0</td>
          <td>5,277,254,000,000.0</td>
          <td>5,321,450,000,000.0</td>
          <td>5,237,202,000,000.0</td>
          <td>5,589,108,000,000.0</td>
          <td>4,526,595,000,000.0</td>
          <td>4,621,780,000,000.0</td>
        </tr>
        <tr>
          <th>25</th>
          <td>dart_OtherNonCurrentAssets</td>
          <td>기타비유동자산</td>
          <td>Other non-current assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>비유동자산</td>
          <td>기타비유동자산</td>
          <td>None</td>
          <td>7,683,168,000,000.0</td>
          <td>6,776,566,000,000.0</td>
          <td>...</td>
          <td>4,099,387,000,000.0</td>
          <td>4,360,259,000,000.0</td>
          <td>4,364,445,000,000.0</td>
          <td>4,248,376,000,000.0</td>
          <td>2,832,583,000,000.0</td>
          <td>1,572,027,000,000.0</td>
          <td>2,541,290,000,000.0</td>
          <td>1,999,038,000,000.0</td>
          <td>2,334,818,000,000.0</td>
          <td>3,089,524,000,000.0</td>
        </tr>
        <tr>
          <th>26</th>
          <td>ifrs_Assets</td>
          <td>자산총계</td>
          <td>Total assets</td>
          <td>재무상태표 [abstract]</td>
          <td>자산 [abstract]</td>
          <td>자산총계</td>
          <td>None</td>
          <td>None</td>
          <td>339,357,244,000,000.0</td>
          <td>337,195,786,000,000.0</td>
          <td>...</td>
          <td>312,473,113,000,000.0</td>
          <td>301,752,090,000,000.0</td>
          <td>296,578,579,000,000.0</td>
          <td>277,589,436,000,000.0</td>
          <td>264,217,372,000,000.0</td>
          <td>262,174,324,000,000.0</td>
          <td>244,471,456,000,000.0</td>
          <td>242,179,521,000,000.0</td>
          <td>230,422,958,000,000.0</td>
          <td>214,075,018,000,000.0</td>
        </tr>
        <tr>
          <th>27</th>
          <td>ifrs_CurrentLiabilities</td>
          <td>유동부채</td>
          <td>Current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>None</td>
          <td>None</td>
          <td>69,081,510,000,000.0</td>
          <td>74,705,872,000,000.0</td>
          <td>...</td>
          <td>68,298,586,000,000.0</td>
          <td>67,175,114,000,000.0</td>
          <td>66,172,585,000,000.0</td>
          <td>58,468,431,000,000.0</td>
          <td>56,843,132,000,000.0</td>
          <td>54,704,095,000,000.0</td>
          <td>50,459,481,000,000.0</td>
          <td>50,502,909,000,000.0</td>
          <td>52,013,913,000,000.0</td>
          <td>51,315,409,000,000.0</td>
        </tr>
        <tr>
          <th>28</th>
          <td>entity00126380_udf_BS_20171018222617796_Curren...</td>
          <td>매입채무</td>
          <td>Account payable Trade</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>매입채무</td>
          <td>None</td>
          <td>8,479,916,000,000.0</td>
          <td>10,209,231,000,000.0</td>
          <td>...</td>
          <td>9,301,132,000,000.0</td>
          <td>9,083,907,000,000.0</td>
          <td>11,367,405,000,000.0</td>
          <td>9,075,774,000,000.0</td>
          <td>9,569,549,000,000.0</td>
          <td>6,485,039,000,000.0</td>
          <td>7,857,285,000,000.0</td>
          <td>6,187,291,000,000.0</td>
          <td>7,914,704,000,000.0</td>
          <td>8,437,139,000,000.0</td>
        </tr>
        <tr>
          <th>29</th>
          <td>ifrs_ShorttermBorrowings</td>
          <td>단기차입금</td>
          <td>Short-term borrowings</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>단기차입금</td>
          <td>None</td>
          <td>13,586,660,000,000.0</td>
          <td>18,826,524,000,000.0</td>
          <td>...</td>
          <td>9,973,335,000,000.0</td>
          <td>15,767,619,000,000.0</td>
          <td>15,329,338,000,000.0</td>
          <td>13,767,140,000,000.0</td>
          <td>9,519,010,000,000.0</td>
          <td>12,746,789,000,000.0</td>
          <td>10,771,299,000,000.0</td>
          <td>11,155,425,000,000.0</td>
          <td>8,029,299,000,000.0</td>
          <td>6,438,517,000,000.0</td>
        </tr>
        <tr>
          <th>30</th>
          <td>entity00126380_udf_BS_20171018222642264_Curren...</td>
          <td>미지급금</td>
          <td>Other payble</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>미지급금</td>
          <td>None</td>
          <td>10,711,536,000,000.0</td>
          <td>9,404,608,000,000.0</td>
          <td>...</td>
          <td>15,036,480,000,000.0</td>
          <td>13,899,633,000,000.0</td>
          <td>13,755,728,000,000.0</td>
          <td>12,878,541,000,000.0</td>
          <td>16,072,700,000,000.0</td>
          <td>11,525,910,000,000.0</td>
          <td>8,986,065,000,000.0</td>
          <td>8,864,378,000,000.0</td>
          <td>10,318,407,000,000.0</td>
          <td>9,196,566,000,000.0</td>
        </tr>
        <tr>
          <th>31</th>
          <td>entity00126380_udf_BS_20171018222640707_Curren...</td>
          <td>선수금</td>
          <td>Advance received</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>선수금</td>
          <td>None</td>
          <td>820,265,000,000.0</td>
          <td>938,553,000,000.0</td>
          <td>...</td>
          <td>1,135,681,000,000.0</td>
          <td>1,249,174,000,000.0</td>
          <td>1,360,407,000,000.0</td>
          <td>1,230,965,000,000.0</td>
          <td>1,101,841,000,000.0</td>
          <td>1,358,878,000,000.0</td>
          <td>1,208,197,000,000.0</td>
          <td>1,343,432,000,000.0</td>
          <td>1,427,230,000,000.0</td>
          <td>1,706,313,000,000.0</td>
        </tr>
        <tr>
          <th>32</th>
          <td>entity00126380_udf_BS_20171018222637261_Curren...</td>
          <td>예수금</td>
          <td>Withholdings</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>예수금</td>
          <td>None</td>
          <td>951,254,000,000.0</td>
          <td>825,190,000,000.0</td>
          <td>...</td>
          <td>821,190,000,000.0</td>
          <td>793,582,000,000.0</td>
          <td>680,210,000,000.0</td>
          <td>792,770,000,000.0</td>
          <td>551,452,000,000.0</td>
          <td>685,028,000,000.0</td>
          <td>1,117,805,000,000.0</td>
          <td>992,733,000,000.0</td>
          <td>1,161,635,000,000.0</td>
          <td>1,176,046,000,000.0</td>
        </tr>
        <tr>
          <th>33</th>
          <td>entity00126380_udf_BS_20171018222635206_Curren...</td>
          <td>미지급비용</td>
          <td>Accrued expense</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>미지급비용</td>
          <td>None</td>
          <td>20,339,687,000,000.0</td>
          <td>16,331,192,000,000.0</td>
          <td>...</td>
          <td>15,288,788,000,000.0</td>
          <td>13,996,273,000,000.0</td>
          <td>9,983,738,000,000.0</td>
          <td>9,942,883,000,000.0</td>
          <td>9,214,385,000,000.0</td>
          <td>12,527,300,000,000.0</td>
          <td>9,955,813,000,000.0</td>
          <td>11,628,739,000,000.0</td>
          <td>12,876,777,000,000.0</td>
          <td>11,344,530,000,000.0</td>
        </tr>
        <tr>
          <th>34</th>
          <td>dart_PaymentsOfIncomeTaxesPayable</td>
          <td>미지급법인세</td>
          <td>Payments of income taxes payable</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>미지급법인세</td>
          <td>None</td>
          <td>8,720,050,000,000.0</td>
          <td>8,822,613,000,000.0</td>
          <td>...</td>
          <td>10,542,578,000,000.0</td>
          <td>7,408,348,000,000.0</td>
          <td>5,446,061,000,000.0</td>
          <td>3,472,232,000,000.0</td>
          <td>3,422,182,000,000.0</td>
          <td>2,837,353,000,000.0</td>
          <td>1,782,134,000,000.0</td>
          <td>3,401,625,000,000.0</td>
          <td>2,161,109,000,000.0</td>
          <td>3,386,018,000,000.0</td>
        </tr>
        <tr>
          <th>35</th>
          <td>entity00126380_udf_BS_20171024141934989_Curren...</td>
          <td>유동성장기부채</td>
          <td>Current portion of long-term borrowings and de...</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>유동성장기부채</td>
          <td>None</td>
          <td>33,386,000,000.0</td>
          <td>1,799,346,000,000.0</td>
          <td>...</td>
          <td>15,631,000,000.0</td>
          <td>278,619,000,000.0</td>
          <td>17,659,000,000.0</td>
          <td>26,585,000,000.0</td>
          <td>1,139,042,000,000.0</td>
          <td>1,232,817,000,000.0</td>
          <td>1,319,602,000,000.0</td>
          <td>221,548,000,000.0</td>
          <td>1,778,667,000,000.0</td>
          <td>2,425,831,000,000.0</td>
        </tr>
        <tr>
          <th>36</th>
          <td>ifrs_CurrentProvisions</td>
          <td>충당부채</td>
          <td>Current provisions</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>충당부채</td>
          <td>None</td>
          <td>4,384,038,000,000.0</td>
          <td>6,400,043,000,000.0</td>
          <td>...</td>
          <td>5,254,798,000,000.0</td>
          <td>4,294,820,000,000.0</td>
          <td>7,386,454,000,000.0</td>
          <td>6,404,954,000,000.0</td>
          <td>5,535,077,000,000.0</td>
          <td>4,597,417,000,000.0</td>
          <td>6,788,901,000,000.0</td>
          <td>6,420,603,000,000.0</td>
          <td>5,991,510,000,000.0</td>
          <td>6,736,476,000,000.0</td>
        </tr>
        <tr>
          <th>37</th>
          <td>dart_OtherCurrentLiabilities</td>
          <td>기타유동부채</td>
          <td>Other current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>기타유동부채</td>
          <td>None</td>
          <td>1,054,718,000,000.0</td>
          <td>1,148,572,000,000.0</td>
          <td>...</td>
          <td>928,973,000,000.0</td>
          <td>403,139,000,000.0</td>
          <td>401,522,000,000.0</td>
          <td>445,164,000,000.0</td>
          <td>344,821,000,000.0</td>
          <td>351,176,000,000.0</td>
          <td>341,017,000,000.0</td>
          <td>287,135,000,000.0</td>
          <td>326,259,000,000.0</td>
          <td>467,973,000,000.0</td>
        </tr>
        <tr>
          <th>38</th>
          <td>ifrs_LiabilitiesIncludedInDisposalGroupsClassi...</td>
          <td>매각예정분류부채</td>
          <td>Liabilities included in disposal groups classi...</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>유동부채</td>
          <td>매각예정분류부채</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>...</td>
          <td>nan</td>
          <td>nan</td>
          <td>444,063,000,000.0</td>
          <td>431,423,000,000.0</td>
          <td>373,073,000,000.0</td>
          <td>356,388,000,000.0</td>
          <td>331,363,000,000.0</td>
          <td>nan</td>
          <td>28,316,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>39</th>
          <td>ifrs_NoncurrentLiabilities</td>
          <td>비유동부채</td>
          <td>Non-current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>None</td>
          <td>None</td>
          <td>22,522,557,000,000.0</td>
          <td>20,386,754,000,000.0</td>
          <td>...</td>
          <td>20,914,647,000,000.0</td>
          <td>20,085,548,000,000.0</td>
          <td>19,714,743,000,000.0</td>
          <td>18,415,257,000,000.0</td>
          <td>17,556,285,000,000.0</td>
          <td>14,507,196,000,000.0</td>
          <td>14,475,596,000,000.0</td>
          <td>12,616,807,000,000.0</td>
          <td>10,320,857,000,000.0</td>
          <td>12,743,599,000,000.0</td>
        </tr>
        <tr>
          <th>40</th>
          <td>dart_BondsIssued</td>
          <td>사채</td>
          <td>Bonds issued</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>사채</td>
          <td>None</td>
          <td>961,972,000,000.0</td>
          <td>972,435,000,000.0</td>
          <td>...</td>
          <td>961,780,000,000.0</td>
          <td>953,361,000,000.0</td>
          <td>1,015,061,000,000.0</td>
          <td>1,000,508,000,000.0</td>
          <td>950,273,000,000.0</td>
          <td>58,542,000,000.0</td>
          <td>53,042,000,000.0</td>
          <td>1,230,448,000,000.0</td>
          <td>1,355,882,000,000.0</td>
          <td>1,311,068,000,000.0</td>
        </tr>
        <tr>
          <th>41</th>
          <td>dart_LongTermBorrowingsGross</td>
          <td>장기차입금</td>
          <td>Long-term borrowings, gross</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>장기차입금</td>
          <td>None</td>
          <td>85,085,000,000.0</td>
          <td>87,101,000,000.0</td>
          <td>...</td>
          <td>1,910,470,000,000.0</td>
          <td>1,814,446,000,000.0</td>
          <td>2,199,998,000,000.0</td>
          <td>1,917,571,000,000.0</td>
          <td>1,640,979,000,000.0</td>
          <td>1,244,238,000,000.0</td>
          <td>813,355,000,000.0</td>
          <td>266,542,000,000.0</td>
          <td>101,671,000,000.0</td>
          <td>985,117,000,000.0</td>
        </tr>
        <tr>
          <th>42</th>
          <td>dart_LongTermOtherPayablesGross</td>
          <td>장기미지급금</td>
          <td>Long-Term other Payables, gross</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>장기미지급금</td>
          <td>None</td>
          <td>3,194,043,000,000.0</td>
          <td>1,688,167,000,000.0</td>
          <td>...</td>
          <td>1,935,019,000,000.0</td>
          <td>2,043,729,000,000.0</td>
          <td>1,999,578,000,000.0</td>
          <td>1,927,517,000,000.0</td>
          <td>2,580,785,000,000.0</td>
          <td>3,317,054,000,000.0</td>
          <td>3,263,099,000,000.0</td>
          <td>3,041,687,000,000.0</td>
          <td>2,562,271,000,000.0</td>
          <td>1,053,756,000,000.0</td>
        </tr>
        <tr>
          <th>43</th>
          <td>dart_PostemploymentBenefitObligations</td>
          <td>순확정급여부채</td>
          <td>Post-employment benefit obligations</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>순확정급여부채</td>
          <td>None</td>
          <td>504,064,000,000.0</td>
          <td>524,088,000,000.0</td>
          <td>...</td>
          <td>425,561,000,000.0</td>
          <td>389,922,000,000.0</td>
          <td>594,158,000,000.0</td>
          <td>540,759,000,000.0</td>
          <td>469,855,000,000.0</td>
          <td>173,656,000,000.0</td>
          <td>1,156,642,000,000.0</td>
          <td>358,820,000,000.0</td>
          <td>201,342,000,000.0</td>
          <td>1,854,902,000,000.0</td>
        </tr>
        <tr>
          <th>44</th>
          <td>ifrs_DeferredTaxLiabilities</td>
          <td>이연법인세부채</td>
          <td>Deferred tax liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>이연법인세부채</td>
          <td>None</td>
          <td>15,162,523,000,000.0</td>
          <td>13,750,490,000,000.0</td>
          <td>...</td>
          <td>12,349,990,000,000.0</td>
          <td>11,710,781,000,000.0</td>
          <td>10,353,456,000,000.0</td>
          <td>9,803,623,000,000.0</td>
          <td>8,981,421,000,000.0</td>
          <td>7,293,514,000,000.0</td>
          <td>6,594,779,000,000.0</td>
          <td>5,154,792,000,000.0</td>
          <td>4,097,811,000,000.0</td>
          <td>6,012,371,000,000.0</td>
        </tr>
        <tr>
          <th>45</th>
          <td>dart_LongTermTradeAndOtherNonCurrentPayables</td>
          <td>장기충당부채</td>
          <td>Long-term trade and other non-current payables</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>장기충당부채</td>
          <td>None</td>
          <td>663,619,000,000.0</td>
          <td>1,123,150,000,000.0</td>
          <td>...</td>
          <td>513,347,000,000.0</td>
          <td>464,324,000,000.0</td>
          <td>635,329,000,000.0</td>
          <td>571,930,000,000.0</td>
          <td>412,552,000,000.0</td>
          <td>358,126,000,000.0</td>
          <td>666,124,000,000.0</td>
          <td>522,378,000,000.0</td>
          <td>499,290,000,000.0</td>
          <td>460,924,000,000.0</td>
        </tr>
        <tr>
          <th>46</th>
          <td>dart_OtherNonCurrentLiabilities</td>
          <td>기타비유동부채</td>
          <td>Other non-current liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>비유동부채</td>
          <td>기타비유동부채</td>
          <td>None</td>
          <td>1,951,251,000,000.0</td>
          <td>2,241,323,000,000.0</td>
          <td>...</td>
          <td>2,818,480,000,000.0</td>
          <td>2,708,985,000,000.0</td>
          <td>2,917,163,000,000.0</td>
          <td>2,653,349,000,000.0</td>
          <td>2,520,420,000,000.0</td>
          <td>2,062,066,000,000.0</td>
          <td>1,928,555,000,000.0</td>
          <td>2,042,140,000,000.0</td>
          <td>1,502,590,000,000.0</td>
          <td>1,065,461,000,000.0</td>
        </tr>
        <tr>
          <th>47</th>
          <td>ifrs_Liabilities</td>
          <td>부채총계</td>
          <td>Total liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>부채 [abstract]</td>
          <td>부채총계</td>
          <td>None</td>
          <td>None</td>
          <td>91,604,067,000,000.0</td>
          <td>95,092,626,000,000.0</td>
          <td>...</td>
          <td>89,213,233,000,000.0</td>
          <td>87,260,662,000,000.0</td>
          <td>85,887,328,000,000.0</td>
          <td>76,883,688,000,000.0</td>
          <td>74,399,417,000,000.0</td>
          <td>69,211,291,000,000.0</td>
          <td>64,935,077,000,000.0</td>
          <td>63,119,716,000,000.0</td>
          <td>62,334,770,000,000.0</td>
          <td>64,059,008,000,000.0</td>
        </tr>
        <tr>
          <th>48</th>
          <td>ifrs_EquityAttributableToOwnersOfParent</td>
          <td>지배기업 소유주지분</td>
          <td>Equity attributable to owners of parent</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>None</td>
          <td>None</td>
          <td>240,068,993,000,000.0</td>
          <td>234,476,380,000,000.0</td>
          <td>...</td>
          <td>215,884,505,000,000.0</td>
          <td>207,213,416,000,000.0</td>
          <td>203,504,410,000,000.0</td>
          <td>193,654,461,000,000.0</td>
          <td>183,119,607,000,000.0</td>
          <td>186,424,328,000,000.0</td>
          <td>173,269,659,000,000.0</td>
          <td>172,876,767,000,000.0</td>
          <td>162,181,725,000,000.0</td>
          <td>144,442,616,000,000.0</td>
        </tr>
        <tr>
          <th>49</th>
          <td>ifrs_IssuedCapital</td>
          <td>자본금</td>
          <td>Issued capital</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>자본금</td>
          <td>None</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>...</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
          <td>897,514,000,000.0</td>
        </tr>
        <tr>
          <th>50</th>
          <td>dart_IssuedCapitalOfPreferredStock</td>
          <td>우선주자본금</td>
          <td>Issued capital of preferred stock</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>자본금</td>
          <td>우선주자본금</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>...</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
          <td>119,467,000,000.0</td>
        </tr>
        <tr>
          <th>51</th>
          <td>dart_IssuedCapitalOfCommonStock</td>
          <td>보통주자본금</td>
          <td>Issued capital of common stock</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>자본금</td>
          <td>보통주자본금</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>...</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
          <td>778,047,000,000.0</td>
        </tr>
        <tr>
          <th>52</th>
          <td>ifrs_SharePremium</td>
          <td>주식발행초과금</td>
          <td>Share premium</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>주식발행초과금</td>
          <td>None</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>...</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
          <td>4,403,893,000,000.0</td>
        </tr>
        <tr>
          <th>53</th>
          <td>ifrs_RetainedEarnings</td>
          <td>이익잉여금</td>
          <td>Retained earnings</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>이익잉여금</td>
          <td>None</td>
          <td>242,698,956,000,000.0</td>
          <td>241,628,322,000,000.0</td>
          <td>...</td>
          <td>222,485,398,000,000.0</td>
          <td>215,811,200,000,000.0</td>
          <td>206,773,005,000,000.0</td>
          <td>199,223,959,000,000.0</td>
          <td>196,724,497,000,000.0</td>
          <td>193,086,317,000,000.0</td>
          <td>186,169,137,000,000.0</td>
          <td>185,132,014,000,000.0</td>
          <td>169,529,604,000,000.0</td>
          <td>148,600,282,000,000.0</td>
        </tr>
        <tr>
          <th>54</th>
          <td>dart_ElementsOfOtherStockholdersEquity</td>
          <td>기타자본항목</td>
          <td>Elements of other stockholder's equity</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>기타자본항목</td>
          <td>None</td>
          <td>-7,931,370,000,000.0</td>
          <td>-12,453,349,000,000.0</td>
          <td>...</td>
          <td>-11,902,300,000,000.0</td>
          <td>-13,899,191,000,000.0</td>
          <td>-8,525,520,000,000.0</td>
          <td>-10,870,453,000,000.0</td>
          <td>-18,892,482,000,000.0</td>
          <td>-11,934,586,000,000.0</td>
          <td>-18,181,791,000,000.0</td>
          <td>-17,580,451,000,000.0</td>
          <td>-12,729,387,000,000.0</td>
          <td>-9,459,073,000,000.0</td>
        </tr>
        <tr>
          <th>55</th>
          <td>dart_OtherComprehensiveIncomeLossAccumulatedAm...</td>
          <td>매각예정분류기타자본항목</td>
          <td>Other Comprehensive income/loss accumulated am...</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>지배기업 소유주지분</td>
          <td>매각예정분류기타자본항목</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>...</td>
          <td>nan</td>
          <td>nan</td>
          <td>-44,482,000,000.0</td>
          <td>-452,000,000.0</td>
          <td>-13,815,000,000.0</td>
          <td>-28,810,000,000.0</td>
          <td>-19,094,000,000.0</td>
          <td>23,797,000,000.0</td>
          <td>80,101,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>56</th>
          <td>ifrs_NoncontrollingInterests</td>
          <td>비지배지분</td>
          <td>Non-controlling interests</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>비지배지분</td>
          <td>None</td>
          <td>None</td>
          <td>7,684,184,000,000.0</td>
          <td>7,626,780,000,000.0</td>
          <td>...</td>
          <td>7,375,375,000,000.0</td>
          <td>7,278,012,000,000.0</td>
          <td>7,186,841,000,000.0</td>
          <td>7,051,287,000,000.0</td>
          <td>6,698,348,000,000.0</td>
          <td>6,538,705,000,000.0</td>
          <td>6,266,720,000,000.0</td>
          <td>6,183,038,000,000.0</td>
          <td>5,906,463,000,000.0</td>
          <td>5,573,394,000,000.0</td>
        </tr>
        <tr>
          <th>57</th>
          <td>ifrs_Equity</td>
          <td>자본총계</td>
          <td>Total equity</td>
          <td>재무상태표 [abstract]</td>
          <td>자본 [abstract]</td>
          <td>자본총계</td>
          <td>None</td>
          <td>None</td>
          <td>247,753,177,000,000.0</td>
          <td>242,103,160,000,000.0</td>
          <td>...</td>
          <td>223,259,880,000,000.0</td>
          <td>214,491,428,000,000.0</td>
          <td>210,691,251,000,000.0</td>
          <td>200,705,748,000,000.0</td>
          <td>189,817,955,000,000.0</td>
          <td>192,963,033,000,000.0</td>
          <td>179,536,379,000,000.0</td>
          <td>179,059,805,000,000.0</td>
          <td>168,088,188,000,000.0</td>
          <td>150,016,010,000,000.0</td>
        </tr>
        <tr>
          <th>58</th>
          <td>ifrs_EquityAndLiabilities</td>
          <td>자본과부채총계</td>
          <td>Total equity and liabilities</td>
          <td>재무상태표 [abstract]</td>
          <td>자본과부채총계</td>
          <td>None</td>
          <td>None</td>
          <td>None</td>
          <td>339,357,244,000,000.0</td>
          <td>337,195,786,000,000.0</td>
          <td>...</td>
          <td>312,473,113,000,000.0</td>
          <td>301,752,090,000,000.0</td>
          <td>296,578,579,000,000.0</td>
          <td>277,589,436,000,000.0</td>
          <td>264,217,372,000,000.0</td>
          <td>262,174,324,000,000.0</td>
          <td>244,471,456,000,000.0</td>
          <td>242,179,521,000,000.0</td>
          <td>230,422,958,000,000.0</td>
          <td>214,075,018,000,000.0</td>
        </tr>
      </tbody>
    </table>
    <p>59 rows × 21 columns</p>
    </div>



4.5 연결 손익계산서
~~~~~~~~~~~~~~~~~~~

.. code:: ipython3

    samsung_electronics.get_financial_statement(start_dt='20120101', fs_tp='is')


.. parsed-literal::

    Loading report - annual: 100%|██████████| 7/7 [00:08<00:00,  1.31s/page]
    



.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>concept_id</th>
          <th>label_ko</th>
          <th>label_en</th>
          <th>class0</th>
          <th>class1</th>
          <th>class2</th>
          <th>[2018-01-01,2018-12-31]연결재무제표</th>
          <th>[2017-01-01,2017-12-31]연결재무제표</th>
          <th>[2016-01-01,2016-12-31]연결재무제표</th>
          <th>[2015-01-01,2015-12-31]연결재무제표</th>
          <th>[2014-01-01,2014-12-31]연결재무제표</th>
          <th>[2013-01-01,2013-12-31]연결재무제표</th>
          <th>[2012-01-01,2012-12-31]연결재무제표</th>
          <th>[2011-01-01,2011-12-31]연결재무제표</th>
          <th>[2010-01-01,2010-12-31]연결재무제표</th>
          <th>[2009-01-01,2009-12-31]연결재무제표</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>ifrs_Revenue</td>
          <td>수익(매출액)</td>
          <td>Revenue(Sales)</td>
          <td>손익계산서 [abstract]</td>
          <td>수익(매출액)</td>
          <td>None</td>
          <td>243,771,415,000,000.0</td>
          <td>239,575,376,000,000.0</td>
          <td>201,866,745,000,000.0</td>
          <td>200,653,482,000,000.0</td>
          <td>206,205,987,000,000.0</td>
          <td>228,692,667,000,000.0</td>
          <td>201,103,613,000,000.0</td>
          <td>165,001,771,000,000.0</td>
          <td>154,630,328,000,000.0</td>
          <td>136,323,670,000,000.0</td>
        </tr>
        <tr>
          <th>1</th>
          <td>ifrs_CostOfSales</td>
          <td>매출원가</td>
          <td>Cost of sales</td>
          <td>손익계산서 [abstract]</td>
          <td>매출원가</td>
          <td>None</td>
          <td>132,394,411,000,000.0</td>
          <td>129,290,661,000,000.0</td>
          <td>120,277,715,000,000.0</td>
          <td>123,482,118,000,000.0</td>
          <td>128,278,800,000,000.0</td>
          <td>137,696,309,000,000.0</td>
          <td>126,651,931,000,000.0</td>
          <td>112,145,120,000,000.0</td>
          <td>102,666,824,000,000.0</td>
          <td>94,594,863,000,000.0</td>
        </tr>
        <tr>
          <th>2</th>
          <td>ifrs_GrossProfit</td>
          <td>매출총이익</td>
          <td>Gross profit</td>
          <td>손익계산서 [abstract]</td>
          <td>매출총이익</td>
          <td>None</td>
          <td>111,377,004,000,000.0</td>
          <td>110,284,715,000,000.0</td>
          <td>81,589,030,000,000.0</td>
          <td>77,171,364,000,000.0</td>
          <td>77,927,187,000,000.0</td>
          <td>90,996,358,000,000.0</td>
          <td>74,451,682,000,000.0</td>
          <td>52,856,651,000,000.0</td>
          <td>51,963,504,000,000.0</td>
          <td>41,728,807,000,000.0</td>
        </tr>
        <tr>
          <th>3</th>
          <td>dart_TotalSellingGeneralAdministrativeExpenses</td>
          <td>판매비와관리비</td>
          <td>Selling general administrative expenses</td>
          <td>손익계산서 [abstract]</td>
          <td>판매비와관리비</td>
          <td>None</td>
          <td>52,490,335,000,000.0</td>
          <td>56,639,677,000,000.0</td>
          <td>52,348,358,000,000.0</td>
          <td>50,757,922,000,000.0</td>
          <td>52,902,116,000,000.0</td>
          <td>54,211,345,000,000.0</td>
          <td>45,402,344,000,000.0</td>
          <td>37,212,360,000,000.0</td>
          <td>35,206,958,000,000.0</td>
          <td>23,362,086,000,000.0</td>
        </tr>
        <tr>
          <th>4</th>
          <td>dart_OperatingIncomeLoss</td>
          <td>영업이익(손실)</td>
          <td>Operating income(loss)</td>
          <td>손익계산서 [abstract]</td>
          <td>영업이익(손실)</td>
          <td>None</td>
          <td>58,886,669,000,000.0</td>
          <td>53,645,038,000,000.0</td>
          <td>29,240,672,000,000.0</td>
          <td>26,413,442,000,000.0</td>
          <td>25,025,071,000,000.0</td>
          <td>36,785,013,000,000.0</td>
          <td>29,049,338,000,000.0</td>
          <td>15,644,291,000,000.0</td>
          <td>16,756,546,000,000.0</td>
          <td>10,925,259,000,000.0</td>
        </tr>
        <tr>
          <th>5</th>
          <td>dart_OtherGains</td>
          <td>기타수익</td>
          <td>Other gains</td>
          <td>손익계산서 [abstract]</td>
          <td>기타수익</td>
          <td>None</td>
          <td>1,485,037,000,000.0</td>
          <td>3,010,657,000,000.0</td>
          <td>3,238,261,000,000.0</td>
          <td>1,685,947,000,000.0</td>
          <td>3,801,357,000,000.0</td>
          <td>2,429,551,000,000.0</td>
          <td>1,552,989,000,000.0</td>
          <td>2,251,019,000,000.0</td>
          <td>1,651,808,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>6</th>
          <td>dart_OtherLosses</td>
          <td>기타비용</td>
          <td>Other losses</td>
          <td>손익계산서 [abstract]</td>
          <td>기타비용</td>
          <td>None</td>
          <td>1,142,018,000,000.0</td>
          <td>1,419,648,000,000.0</td>
          <td>2,463,814,000,000.0</td>
          <td>3,723,434,000,000.0</td>
          <td>2,259,737,000,000.0</td>
          <td>1,614,048,000,000.0</td>
          <td>1,576,025,000,000.0</td>
          <td>1,612,690,000,000.0</td>
          <td>1,064,680,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>7</th>
          <td>entity00126380_udf_IS_2017102191515184_IncomeS...</td>
          <td>지분법이익</td>
          <td>Share of profit (loss) of associates and joint...</td>
          <td>손익계산서 [abstract]</td>
          <td>지분법이익</td>
          <td>None</td>
          <td>539,845,000,000.0</td>
          <td>201,442,000,000.0</td>
          <td>19,501,000,000.0</td>
          <td>1,101,932,000,000.0</td>
          <td>342,516,000,000.0</td>
          <td>504,063,000,000.0</td>
          <td>986,611,000,000.0</td>
          <td>1,399,194,000,000.0</td>
          <td>2,267,091,000,000.0</td>
          <td>1,713,299,000,000.0</td>
        </tr>
        <tr>
          <th>8</th>
          <td>ifrs_FinanceIncome</td>
          <td>금융수익</td>
          <td>Finance income</td>
          <td>손익계산서 [abstract]</td>
          <td>금융수익</td>
          <td>None</td>
          <td>9,999,321,000,000.0</td>
          <td>9,737,391,000,000.0</td>
          <td>11,385,645,000,000.0</td>
          <td>10,514,879,000,000.0</td>
          <td>8,259,829,000,000.0</td>
          <td>8,014,672,000,000.0</td>
          <td>7,836,554,000,000.0</td>
          <td>7,403,525,000,000.0</td>
          <td>7,465,128,000,000.0</td>
          <td>9,727,257,000,000.0</td>
        </tr>
        <tr>
          <th>9</th>
          <td>entity00126380_udf_IS_2017102191643789_IncomeS...</td>
          <td>금융비용</td>
          <td>Finance expense</td>
          <td>손익계산서 [abstract]</td>
          <td>금융비용</td>
          <td>None</td>
          <td>8,608,896,000,000.0</td>
          <td>8,978,913,000,000.0</td>
          <td>10,706,613,000,000.0</td>
          <td>10,031,771,000,000.0</td>
          <td>7,294,002,000,000.0</td>
          <td>7,754,972,000,000.0</td>
          <td>7,934,450,000,000.0</td>
          <td>7,893,421,000,000.0</td>
          <td>7,700,099,000,000.0</td>
          <td>10,174,219,000,000.0</td>
        </tr>
        <tr>
          <th>10</th>
          <td>ifrs_ProfitLossBeforeTax</td>
          <td>법인세비용차감전순이익(손실)</td>
          <td>Profit (loss) before tax</td>
          <td>손익계산서 [abstract]</td>
          <td>법인세비용차감전순이익(손실)</td>
          <td>None</td>
          <td>61,159,958,000,000.0</td>
          <td>56,195,967,000,000.0</td>
          <td>30,713,652,000,000.0</td>
          <td>25,960,995,000,000.0</td>
          <td>27,875,034,000,000.0</td>
          <td>38,364,279,000,000.0</td>
          <td>29,915,017,000,000.0</td>
          <td>17,191,918,000,000.0</td>
          <td>19,375,794,000,000.0</td>
          <td>12,191,596,000,000.0</td>
        </tr>
        <tr>
          <th>11</th>
          <td>ifrs_IncomeTaxExpenseContinuingOperations</td>
          <td>법인세비용</td>
          <td>Income tax expense</td>
          <td>손익계산서 [abstract]</td>
          <td>법인세비용</td>
          <td>None</td>
          <td>16,815,101,000,000.0</td>
          <td>14,009,220,000,000.0</td>
          <td>7,987,560,000,000.0</td>
          <td>6,900,851,000,000.0</td>
          <td>4,480,676,000,000.0</td>
          <td>7,889,515,000,000.0</td>
          <td>6,069,732,000,000.0</td>
          <td>3,432,875,000,000.0</td>
          <td>3,193,438,000,000.0</td>
          <td>2,431,046,000,000.0</td>
        </tr>
        <tr>
          <th>12</th>
          <td>ifrs_ProfitLossFromContinuingOperations</td>
          <td>계속영업이익(손실)</td>
          <td>Profit (loss) from continuing operations</td>
          <td>손익계산서 [abstract]</td>
          <td>계속영업이익(손실)</td>
          <td>None</td>
          <td>44,344,857,000,000.0</td>
          <td>42,186,747,000,000.0</td>
          <td>22,726,092,000,000.0</td>
          <td>19,060,144,000,000.0</td>
          <td>23,394,358,000,000.0</td>
          <td>30,474,764,000,000.0</td>
          <td>23,845,285,000,000.0</td>
          <td>13,759,043,000,000.0</td>
          <td>16,182,356,000,000.0</td>
          <td>9,760,550,000,000.0</td>
        </tr>
        <tr>
          <th>13</th>
          <td>ifrs_ProfitLoss</td>
          <td>당기순이익(손실)</td>
          <td>Profit (loss)</td>
          <td>손익계산서 [abstract]</td>
          <td>당기순이익(손실)</td>
          <td>None</td>
          <td>44,344,857,000,000.0</td>
          <td>42,186,747,000,000.0</td>
          <td>22,726,092,000,000.0</td>
          <td>19,060,144,000,000.0</td>
          <td>23,394,358,000,000.0</td>
          <td>30,474,764,000,000.0</td>
          <td>23,845,285,000,000.0</td>
          <td>13,759,043,000,000.0</td>
          <td>16,182,356,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>14</th>
          <td>ifrs_ProfitLossAttributableToOwnersOfParent</td>
          <td>지배기업의 소유주에게 귀속되는 당기순이익(손실)</td>
          <td>Profit (loss), attributable to owners of parent</td>
          <td>손익계산서 [abstract]</td>
          <td>당기순이익(손실)의 귀속 [abstract]</td>
          <td>지배기업의 소유주에게 귀속되는 당기순이익(손실)</td>
          <td>43,890,877,000,000.0</td>
          <td>41,344,569,000,000.0</td>
          <td>22,415,655,000,000.0</td>
          <td>18,694,628,000,000.0</td>
          <td>23,082,499,000,000.0</td>
          <td>29,821,215,000,000.0</td>
          <td>23,185,375,000,000.0</td>
          <td>13,382,645,000,000.0</td>
          <td>15,831,674,000,000.0</td>
          <td>9,571,598,000,000.0</td>
        </tr>
        <tr>
          <th>15</th>
          <td>ifrs_ProfitLossAttributableToNoncontrollingInt...</td>
          <td>비지배지분에 귀속되는 당기순이익(손실)</td>
          <td>Profit (loss), attributable to non-controlling...</td>
          <td>손익계산서 [abstract]</td>
          <td>당기순이익(손실)의 귀속 [abstract]</td>
          <td>비지배지분에 귀속되는 당기순이익(손실)</td>
          <td>453,980,000,000.0</td>
          <td>842,178,000,000.0</td>
          <td>310,437,000,000.0</td>
          <td>365,516,000,000.0</td>
          <td>311,859,000,000.0</td>
          <td>653,549,000,000.0</td>
          <td>659,910,000,000.0</td>
          <td>376,398,000,000.0</td>
          <td>350,682,000,000.0</td>
          <td>188,952,000,000.0</td>
        </tr>
        <tr>
          <th>16</th>
          <td>ifrs_BasicEarningsLossPerShare</td>
          <td>기본주당이익(손실)</td>
          <td>Basic earnings (loss) per share</td>
          <td>손익계산서 [abstract]</td>
          <td>주당이익 [abstract]</td>
          <td>기본주당이익(손실)</td>
          <td>6,461.0</td>
          <td>5,997.0</td>
          <td>3,159.0</td>
          <td>126,305,000,000.0</td>
          <td>153,105,000,000.0</td>
          <td>197,841,000,000.0</td>
          <td>154,020,000,000.0</td>
          <td>89,229,000,000.0</td>
          <td>106,211,000,000.0</td>
          <td>64,888,000,000.0</td>
        </tr>
        <tr>
          <th>17</th>
          <td>ifrs_DilutedEarningsLossPerShare</td>
          <td>희석주당이익(손실)</td>
          <td>Diluted earnings (loss) per share</td>
          <td>손익계산서 [abstract]</td>
          <td>주당이익 [abstract]</td>
          <td>희석주당이익(손실)</td>
          <td>6,461.0</td>
          <td>5,997.0</td>
          <td>3,159.0</td>
          <td>126,303,000,000.0</td>
          <td>153,096,000,000.0</td>
          <td>197,800,000,000.0</td>
          <td>153,950,000,000.0</td>
          <td>89,146,000,000.0</td>
          <td>105,890,000,000.0</td>
          <td>64,586,000,000.0</td>
        </tr>
      </tbody>
    </table>
    </div>



4.6 연결 포괄손익계산서
~~~~~~~~~~~~~~~~~~~~~~~

.. code:: ipython3

    samsung_electronics.get_financial_statement(start_dt='20120101', fs_tp='ci')


.. parsed-literal::

    Loading report - annual: 100%|██████████| 7/7 [00:08<00:00,  1.11s/page]
    



.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>concept_id</th>
          <th>label_ko</th>
          <th>label_en</th>
          <th>class0</th>
          <th>class1</th>
          <th>class2</th>
          <th>class3</th>
          <th>[2018-01-01,2018-12-31]연결재무제표</th>
          <th>[2017-01-01,2017-12-31]연결재무제표</th>
          <th>[2016-01-01,2016-12-31]연결재무제표</th>
          <th>[2015-01-01,2015-12-31]연결재무제표</th>
          <th>[2014-01-01,2014-12-31]연결재무제표</th>
          <th>[2013-01-01,2013-12-31]연결재무제표</th>
          <th>[2012-01-01,2012-12-31]연결재무제표</th>
          <th>[2011-01-01,2011-12-31]연결재무제표</th>
          <th>[2010-01-01,2010-12-31]연결재무제표</th>
          <th>[2009-01-01,2009-12-31]연결재무제표</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>ifrs_ProfitLoss</td>
          <td>당기순이익(손실)</td>
          <td>Profit (loss)</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>당기순이익(손실)</td>
          <td>None</td>
          <td>None</td>
          <td>44,344,857,000,000.0</td>
          <td>42,186,747,000,000.0</td>
          <td>22,726,092,000,000.0</td>
          <td>19,060,144,000,000.0</td>
          <td>23,394,358,000,000.0</td>
          <td>30,474,764,000,000.0</td>
          <td>23,845,285,000,000.0</td>
          <td>13,759,043,000,000.0</td>
          <td>16,182,356,000,000.0</td>
          <td>9,760,550,000,000.0</td>
        </tr>
        <tr>
          <th>1</th>
          <td>ifrs_OtherComprehensiveIncome</td>
          <td>기타포괄손익</td>
          <td>Other comprehensive income</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>None</td>
          <td>None</td>
          <td>-12,242,000,000.0</td>
          <td>-5,502,257,000,000.0</td>
          <td>1,991,400,000,000.0</td>
          <td>76,071,000,000.0</td>
          <td>-1,993,414,000,000.0</td>
          <td>-1,006,838,000,000.0</td>
          <td>-1,717,080,000,000.0</td>
          <td>-887,485,000,000.0</td>
          <td>906,465,000,000.0</td>
          <td>-661,706,000,000.0</td>
        </tr>
        <tr>
          <th>2</th>
          <td>dart_OtherComprehensiveIncomeThatWillNotBeRecl...</td>
          <td>후속적으로 당기손익으로 재분류되지 않는 포괄손익</td>
          <td>Other comprehensive income that will not be re...</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>후속적으로 당기손익으로 재분류되지 않는 포괄손익</td>
          <td>None</td>
          <td>-656,647,000,000.0</td>
          <td>407,900,000,000.0</td>
          <td>1,014,040,000,000.0</td>
          <td>288,047,000,000.0</td>
          <td>-720,945,000,000.0</td>
          <td>-213,113,000,000.0</td>
          <td>-504,120,000,000.0</td>
          <td>-385,214,000,000.0</td>
          <td>-235,019,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>3</th>
          <td>entity00126380_udf_IS_2018510181631532_OtherCo...</td>
          <td>기타포괄손익-공정가치금융자산평가손익</td>
          <td>oci-fair value assessment</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>후속적으로 당기손익으로 재분류되지 않는 포괄손익</td>
          <td>기타포괄손익-공정가치금융자산평가손익</td>
          <td>-235,865,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>4</th>
          <td>dart_ShareOfOtherComprehensiveIncomeOfAssociat...</td>
          <td>관계기업 및 공동기업의 기타포괄손익에 대한 지분</td>
          <td>Share of other comprehensive income of associa...</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>후속적으로 당기손익으로 재분류되지 않는 포괄손익</td>
          <td>관계기업 및 공동기업의 기타포괄손익에 대한 지분</td>
          <td>-10,631,000,000.0</td>
          <td>-6,347,000,000.0</td>
          <td>50,438,000,000.0</td>
          <td>24,069,000,000.0</td>
          <td>-10,627,000,000.0</td>
          <td>20,756,000,000.0</td>
          <td>-350,491,000,000.0</td>
          <td>-113,898,000,000.0</td>
          <td>387,457,000,000.0</td>
          <td>49,879,000,000.0</td>
        </tr>
        <tr>
          <th>5</th>
          <td>dart_OtherComprehensiveIncomeNetOfTaxGainsLoss...</td>
          <td>순확정급여부채 재측정요소</td>
          <td>Other comprehensive income, net of tax, gains ...</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>후속적으로 당기손익으로 재분류되지 않는 포괄손익</td>
          <td>순확정급여부채 재측정요소</td>
          <td>-410,151,000,000.0</td>
          <td>414,247,000,000.0</td>
          <td>963,602,000,000.0</td>
          <td>263,978,000,000.0</td>
          <td>-710,318,000,000.0</td>
          <td>-213,113,000,000.0</td>
          <td>-504,120,000,000.0</td>
          <td>-385,214,000,000.0</td>
          <td>-235,019,000,000.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>6</th>
          <td>dart_OtherComprehensiveIncomeThatWillBeReclass...</td>
          <td>후속적으로 당기손익으로 재분류되는 포괄손익</td>
          <td>Other comprehensive income that will be reclas...</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>후속적으로 당기손익으로 재분류되는 포괄손익</td>
          <td>None</td>
          <td>644,405,000,000.0</td>
          <td>-5,910,157,000,000.0</td>
          <td>977,360,000,000.0</td>
          <td>-211,976,000,000.0</td>
          <td>-1,272,469,000,000.0</td>
          <td>-793,725,000,000.0</td>
          <td>-1,212,960,000,000.0</td>
          <td>-502,271,000,000.0</td>
          <td>1,141,484,000,000.0</td>
          <td>-661,706,000,000.0</td>
        </tr>
        <tr>
          <th>7</th>
          <td>ifrs_GainsLossesOnRemeasuringAvailableforsaleF...</td>
          <td>매도가능금융자산평가손익</td>
          <td>Gains (losses) on remeasuring available-for-sa...</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>후속적으로 당기손익으로 재분류되는 포괄손익</td>
          <td>매도가능금융자산평가손익</td>
          <td>nan</td>
          <td>511,207,000,000.0</td>
          <td>-23,839,000,000.0</td>
          <td>-414,961,000,000.0</td>
          <td>-232,105,000,000.0</td>
          <td>186,480,000,000.0</td>
          <td>962,184,000,000.0</td>
          <td>-572,028,000,000.0</td>
          <td>932,384,000,000.0</td>
          <td>108,217,000,000.0</td>
        </tr>
        <tr>
          <th>8</th>
          <td>dart_ShareOfOtherComprehensiveIncomeOfAssociat...</td>
          <td>관계기업 및 공동기업의 기타포괄손익에 대한 지분</td>
          <td>Share of other comprehensive income of associa...</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>후속적으로 당기손익으로 재분류되는 포괄손익</td>
          <td>관계기업 및 공동기업의 기타포괄손익에 대한 지분</td>
          <td>6,688,000,000.0</td>
          <td>-49,256,000,000.0</td>
          <td>-130,337,000,000.0</td>
          <td>-65,330,000,000.0</td>
          <td>-118,305,000,000.0</td>
          <td>20,756,000,000.0</td>
          <td>-350,491,000,000.0</td>
          <td>-113,898,000,000.0</td>
          <td>387,457,000,000.0</td>
          <td>49,879,000,000.0</td>
        </tr>
        <tr>
          <th>9</th>
          <td>ifrs_GainsLossesOnHedgesOfNetInvestmentsInFore...</td>
          <td>해외사업장환산외환차이</td>
          <td>Gains (losses) on hedges of net investments in...</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>후속적으로 당기손익으로 재분류되는 포괄손익</td>
          <td>해외사업장환산외환차이</td>
          <td>590,638,000,000.0</td>
          <td>-6,334,987,000,000.0</td>
          <td>1,131,536,000,000.0</td>
          <td>268,315,000,000.0</td>
          <td>-922,059,000,000.0</td>
          <td>-1,000,961,000,000.0</td>
          <td>-1,824,653,000,000.0</td>
          <td>183,655,000,000.0</td>
          <td>-178,357,000,000.0</td>
          <td>-819,802,000,000.0</td>
        </tr>
        <tr>
          <th>10</th>
          <td>ifrs_GainsLossesOnCashFlowHedgesNetOfTax</td>
          <td>현금흐름위험회피파생상품평가손익</td>
          <td>Gains (losses) on cash flow hedges, net of tax</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>기타포괄손익</td>
          <td>후속적으로 당기손익으로 재분류되는 포괄손익</td>
          <td>현금흐름위험회피파생상품평가손익</td>
          <td>47,079,000,000.0</td>
          <td>-37,121,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>11</th>
          <td>ifrs_ComprehensiveIncome</td>
          <td>총포괄손익</td>
          <td>Total comprehensive income</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>총포괄손익</td>
          <td>None</td>
          <td>None</td>
          <td>44,332,615,000,000.0</td>
          <td>36,684,490,000,000.0</td>
          <td>24,717,492,000,000.0</td>
          <td>19,136,215,000,000.0</td>
          <td>21,400,944,000,000.0</td>
          <td>29,467,926,000,000.0</td>
          <td>22,128,205,000,000.0</td>
          <td>12,871,558,000,000.0</td>
          <td>17,088,821,000,000.0</td>
          <td>9,098,844,000,000.0</td>
        </tr>
        <tr>
          <th>12</th>
          <td>ifrs_ComprehensiveIncomeAttributableToOwnersOf...</td>
          <td>지배기업 소유주지분</td>
          <td>Comprehensive income, attributable to owners o...</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>포괄손익의 귀속</td>
          <td>지배기업 소유주지분</td>
          <td>None</td>
          <td>43,882,473,000,000.0</td>
          <td>35,887,505,000,000.0</td>
          <td>24,310,814,000,000.0</td>
          <td>18,804,189,000,000.0</td>
          <td>20,990,732,000,000.0</td>
          <td>28,837,590,000,000.0</td>
          <td>21,499,343,000,000.0</td>
          <td>12,439,116,000,000.0</td>
          <td>16,720,164,000,000.0</td>
          <td>9,060,689,000,000.0</td>
        </tr>
        <tr>
          <th>13</th>
          <td>ifrs_ComprehensiveIncomeAttributableToNoncontr...</td>
          <td>비지배지분</td>
          <td>Comprehensive income, attributable to non-cont...</td>
          <td>포괄손익계산서 [abstract]</td>
          <td>포괄손익의 귀속</td>
          <td>비지배지분</td>
          <td>None</td>
          <td>450,142,000,000.0</td>
          <td>796,985,000,000.0</td>
          <td>406,678,000,000.0</td>
          <td>332,026,000,000.0</td>
          <td>410,212,000,000.0</td>
          <td>630,336,000,000.0</td>
          <td>628,862,000,000.0</td>
          <td>432,442,000,000.0</td>
          <td>368,657,000,000.0</td>
          <td>38,155,000,000.0</td>
        </tr>
      </tbody>
    </table>
    </div>



4.7 연결 현금흐름표
~~~~~~~~~~~~~~~~~~~

.. code:: ipython3

    samsung_electronics.get_financial_statement(start_dt='20120101', fs_tp='cf')


.. parsed-literal::

    Loading report - annual: 100%|██████████| 7/7 [00:08<00:00,  1.42s/page]
    



.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>concept_id</th>
          <th>label_ko</th>
          <th>label_en</th>
          <th>class0</th>
          <th>class1</th>
          <th>class2</th>
          <th>class3</th>
          <th>[2018-01-01,2018-12-31]연결재무제표</th>
          <th>[2017-01-01,2017-12-31]연결재무제표</th>
          <th>[2016-01-01,2016-12-31]연결재무제표</th>
          <th>[2015-01-01,2015-12-31]연결재무제표</th>
          <th>[2014-01-01,2014-12-31]연결재무제표</th>
          <th>[2013-01-01,2013-12-31]연결재무제표</th>
          <th>[2012-01-01,2012-12-31]연결재무제표</th>
          <th>[2011-01-01,2011-12-31]연결재무제표</th>
          <th>[2010-01-01,2010-12-31]연결재무제표</th>
          <th>[2009-01-01,2009-12-31]연결재무제표</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>ifrs_CashFlowsFromUsedInOperatingActivities</td>
          <td>영업활동 현금흐름</td>
          <td>Cash flows from (used in) operating activities</td>
          <td>현금흐름표 [abstract]</td>
          <td>영업활동 현금흐름</td>
          <td>None</td>
          <td>None</td>
          <td>67,031,863,000,000.0</td>
          <td>62,162,041,000,000.0</td>
          <td>47,385,644,000,000.0</td>
          <td>40,061,761,000,000.0</td>
          <td>36,975,389,000,000.0</td>
          <td>46,707,440,000,000.0</td>
          <td>37,972,809,000,000.0</td>
          <td>22,917,901,000,000.0</td>
          <td>23,826,779,000,000.0</td>
          <td>18,522,468,000,000.0</td>
        </tr>
        <tr>
          <th>1</th>
          <td>entity00126380_udf_CF_201710211099539_CashFlow...</td>
          <td>영업에서 창출된 현금흐름</td>
          <td>Cash flows from operating activities</td>
          <td>현금흐름표 [abstract]</td>
          <td>영업활동 현금흐름</td>
          <td>영업에서 창출된 현금흐름</td>
          <td>None</td>
          <td>78,025,064,000,000.0</td>
          <td>67,777,432,000,000.0</td>
          <td>52,299,610,000,000.0</td>
          <td>43,989,083,000,000.0</td>
          <td>41,880,987,000,000.0</td>
          <td>52,966,351,000,000.0</td>
          <td>40,826,895,000,000.0</td>
          <td>26,152,327,000,000.0</td>
          <td>24,566,813,000,000.0</td>
          <td>20,124,820,000,000.0</td>
        </tr>
        <tr>
          <th>2</th>
          <td>entity00126380_udf_CF_201710211092510_udf_CF_2...</td>
          <td>당기순이익</td>
          <td>Profit</td>
          <td>현금흐름표 [abstract]</td>
          <td>영업활동 현금흐름</td>
          <td>영업에서 창출된 현금흐름</td>
          <td>당기순이익</td>
          <td>44,344,857,000,000.0</td>
          <td>42,186,747,000,000.0</td>
          <td>22,726,092,000,000.0</td>
          <td>19,060,144,000,000.0</td>
          <td>23,394,358,000,000.0</td>
          <td>30,474,764,000,000.0</td>
          <td>23,845,285,000,000.0</td>
          <td>13,759,043,000,000.0</td>
          <td>16,182,356,000,000.0</td>
          <td>9,760,550,000,000.0</td>
        </tr>
        <tr>
          <th>3</th>
          <td>entity00126380_udf_CF_2017102110929616_udf_CF_...</td>
          <td>조정</td>
          <td>Adjustments</td>
          <td>현금흐름표 [abstract]</td>
          <td>영업활동 현금흐름</td>
          <td>영업에서 창출된 현금흐름</td>
          <td>조정</td>
          <td>43,604,573,000,000.0</td>
          <td>36,211,232,000,000.0</td>
          <td>30,754,471,000,000.0</td>
          <td>29,610,971,000,000.0</td>
          <td>22,323,765,000,000.0</td>
          <td>23,804,832,000,000.0</td>
          <td>22,759,559,000,000.0</td>
          <td>16,450,629,000,000.0</td>
          <td>14,052,492,000,000.0</td>
          <td>13,937,675,000,000.0</td>
        </tr>
        <tr>
          <th>4</th>
          <td>entity00126380_udf_CF_2017102110934928_udf_CF_...</td>
          <td>영업활동으로 인한 자산부채의 변동</td>
          <td>NEWAccount for Cash flows from operating activ...</td>
          <td>현금흐름표 [abstract]</td>
          <td>영업활동 현금흐름</td>
          <td>영업에서 창출된 현금흐름</td>
          <td>영업활동으로 인한 자산부채의 변동</td>
          <td>-9,924,366,000,000.0</td>
          <td>-10,620,547,000,000.0</td>
          <td>-1,180,953,000,000.0</td>
          <td>-4,682,032,000,000.0</td>
          <td>-3,837,136,000,000.0</td>
          <td>-1,313,245,000,000.0</td>
          <td>-5,777,949,000,000.0</td>
          <td>-4,057,345,000,000.0</td>
          <td>-5,668,035,000,000.0</td>
          <td>-3,573,405,000,000.0</td>
        </tr>
        <tr>
          <th>5</th>
          <td>ifrs_InterestReceivedClassifiedAsOperatingActi...</td>
          <td>이자의 수취</td>
          <td>Interest received</td>
          <td>현금흐름표 [abstract]</td>
          <td>영업활동 현금흐름</td>
          <td>이자의 수취</td>
          <td>None</td>
          <td>1,788,520,000,000.0</td>
          <td>1,581,117,000,000.0</td>
          <td>1,405,085,000,000.0</td>
          <td>2,151,741,000,000.0</td>
          <td>1,555,373,000,000.0</td>
          <td>1,034,074,000,000.0</td>
          <td>789,397,000,000.0</td>
          <td>755,859,000,000.0</td>
          <td>457,508,000,000.0</td>
          <td>301,795,000,000.0</td>
        </tr>
        <tr>
          <th>6</th>
          <td>ifrs_InterestPaidClassifiedAsOperatingActivities</td>
          <td>이자의 지급</td>
          <td>Interest paid</td>
          <td>현금흐름표 [abstract]</td>
          <td>영업활동 현금흐름</td>
          <td>이자의 지급</td>
          <td>None</td>
          <td>548,272,000,000.0</td>
          <td>542,715,000,000.0</td>
          <td>443,838,000,000.0</td>
          <td>-748,256,000,000.0</td>
          <td>-463,740,000,000.0</td>
          <td>-434,857,000,000.0</td>
          <td>-576,379,000,000.0</td>
          <td>-641,462,000,000.0</td>
          <td>-582,292,000,000.0</td>
          <td>-546,000,000,000.0</td>
        </tr>
        <tr>
          <th>7</th>
          <td>ifrs_DividendsReceivedClassifiedAsOperatingAct...</td>
          <td>배당금 수입</td>
          <td>Dividends received</td>
          <td>현금흐름표 [abstract]</td>
          <td>영업활동 현금흐름</td>
          <td>배당금 수입</td>
          <td>None</td>
          <td>215,992,000,000.0</td>
          <td>173,305,000,000.0</td>
          <td>256,851,000,000.0</td>
          <td>266,369,000,000.0</td>
          <td>1,495,658,000,000.0</td>
          <td>592,217,000,000.0</td>
          <td>1,112,940,000,000.0</td>
          <td>628,585,000,000.0</td>
          <td>1,520,037,000,000.0</td>
          <td>69,392,000,000.0</td>
        </tr>
        <tr>
          <th>8</th>
          <td>ifrs_IncomeTaxesPaidRefundClassifiedAsOperatin...</td>
          <td>법인세 납부액</td>
          <td>Income taxes paid (refund)</td>
          <td>현금흐름표 [abstract]</td>
          <td>영업활동 현금흐름</td>
          <td>법인세 납부액</td>
          <td>None</td>
          <td>12,449,441,000,000.0</td>
          <td>6,827,098,000,000.0</td>
          <td>6,132,064,000,000.0</td>
          <td>-5,597,176,000,000.0</td>
          <td>-7,492,889,000,000.0</td>
          <td>-7,450,345,000,000.0</td>
          <td>-4,180,044,000,000.0</td>
          <td>-3,977,408,000,000.0</td>
          <td>-2,135,287,000,000.0</td>
          <td>-1,974,573,000,000.0</td>
        </tr>
        <tr>
          <th>9</th>
          <td>ifrs_CashFlowsFromUsedInInvestingActivities</td>
          <td>투자활동 현금흐름</td>
          <td>Cash flows from (used in) investing activities</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>None</td>
          <td>None</td>
          <td>-52,240,453,000,000.0</td>
          <td>-49,385,216,000,000.0</td>
          <td>-29,658,675,000,000.0</td>
          <td>-27,167,787,000,000.0</td>
          <td>-32,806,408,000,000.0</td>
          <td>-44,747,019,000,000.0</td>
          <td>-31,321,554,000,000.0</td>
          <td>-21,112,564,000,000.0</td>
          <td>-23,984,877,000,000.0</td>
          <td>-14,177,260,000,000.0</td>
        </tr>
        <tr>
          <th>10</th>
          <td>entity00126380_udf_CF_2017102110167395_CashFlo...</td>
          <td>단기금융상품의 순감소(증가)</td>
          <td>Net outflow in financial assets at fair value ...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>단기금융상품의 순감소(증가)</td>
          <td>None</td>
          <td>-12,368,298,000,000.0</td>
          <td>387,627,000,000.0</td>
          <td>-6,780,610,000,000.0</td>
          <td>-5,762,783,000,000.0</td>
          <td>-1,110,842,000,000.0</td>
          <td>-19,391,643,000,000.0</td>
          <td>-5,965,611,000,000.0</td>
          <td>75,666,000,000.0</td>
          <td>-2,991,820,000,000.0</td>
          <td>-5,078,099,000,000.0</td>
        </tr>
        <tr>
          <th>11</th>
          <td>entity00126380_udf_CF_2018510204028298_CashFlo...</td>
          <td>단기상각후원가금융자산의 순증가</td>
          <td>the acquisition of after depreciation capital ...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>단기상각후원가금융자산의 순증가</td>
          <td>None</td>
          <td>-1,436,844,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>12</th>
          <td>entity00126380_udf_CF_2019311123653300_CashFlo...</td>
          <td>단기당기손익-공정가치금융자산의 순증가</td>
          <td>the acquisition of fair value assessment-income</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>단기당기손익-공정가치금융자산의 순증가</td>
          <td>None</td>
          <td>-139,668,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>13</th>
          <td>dart_ProceedsFromSalesOfAvailableForSaleFinanc...</td>
          <td>단기매도가능금융자산의 처분</td>
          <td>Proceeds from sales of available-for-sale fina...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>단기매도가능금융자산의 처분</td>
          <td>None</td>
          <td>nan</td>
          <td>499,856,000,000.0</td>
          <td>3,010,003,000,000.0</td>
          <td>2,143,384,000,000.0</td>
          <td>1,954,158,000,000.0</td>
          <td>2,533,665,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>14</th>
          <td>dart_PurchaseOfAvailableForSaleFinancialAssets</td>
          <td>단기매도가능금융자산의 취득</td>
          <td>Purchase of available-for-sale financial assets</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>단기매도가능금융자산의 취득</td>
          <td>None</td>
          <td>nan</td>
          <td>nan</td>
          <td>2,129,551,000,000.0</td>
          <td>-509,349,000,000.0</td>
          <td>-2,667,610,000,000.0</td>
          <td>-2,500,002,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>15</th>
          <td>dart_ProceedsFromSalesOfLongTermFinancialInstr...</td>
          <td>장기금융상품의 처분</td>
          <td>Proceeds from sales of long-term financial ins...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>장기금융상품의 처분</td>
          <td>None</td>
          <td>255,850,000,000.0</td>
          <td>1,750,221,000,000.0</td>
          <td>789,862,000,000.0</td>
          <td>3,999,710,000,000.0</td>
          <td>94,089,000,000.0</td>
          <td>96,301,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>16</th>
          <td>dart_PurchaseOfLongTermFinancialInstruments</td>
          <td>장기금융상품의 취득</td>
          <td>Purchase of long-term financial instruments</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>장기금융상품의 취득</td>
          <td>None</td>
          <td>7,678,654,000,000.0</td>
          <td>1,079,355,000,000.0</td>
          <td>1,741,547,000,000.0</td>
          <td>-132,733,000,000.0</td>
          <td>-3,248,374,000,000.0</td>
          <td>-1,616,617,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>17</th>
          <td>dart_ProceedsFromSalesOfNonCurrentAvailableFor...</td>
          <td>장기매도가능금융자산의 처분</td>
          <td>Proceeds from sales of non-current available-f...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>장기매도가능금융자산의 처분</td>
          <td>None</td>
          <td>nan</td>
          <td>191,826,000,000.0</td>
          <td>2,010,356,000,000.0</td>
          <td>200,502,000,000.0</td>
          <td>202,904,000,000.0</td>
          <td>1,691,463,000,000.0</td>
          <td>106,208,000,000.0</td>
          <td>415,096,000,000.0</td>
          <td>9,207,000,000.0</td>
          <td>3,111,000,000.0</td>
        </tr>
        <tr>
          <th>18</th>
          <td>dart_PurchaseOfNonCurrentAvailableForSaleFinan...</td>
          <td>장기매도가능금융자산의 취득</td>
          <td>Purchase of non-current available-for-sale fin...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>장기매도가능금융자산의 취득</td>
          <td>None</td>
          <td>nan</td>
          <td>358,497,000,000.0</td>
          <td>1,498,148,000,000.0</td>
          <td>-232,530,000,000.0</td>
          <td>-6,212,102,000,000.0</td>
          <td>-1,531,356,000,000.0</td>
          <td>-870,249,000,000.0</td>
          <td>-419,678,000,000.0</td>
          <td>-414,978,000,000.0</td>
          <td>-86,616,000,000.0</td>
        </tr>
        <tr>
          <th>19</th>
          <td>dart_PurchaseOfFinancialAssetsHeldToMaturity</td>
          <td>만기보유금융자산의 취득</td>
          <td>Purchase of financial assets held to maturity</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>만기보유금융자산의 취득</td>
          <td>None</td>
          <td>nan</td>
          <td>106,751,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>20</th>
          <td>entity00126380_udf_CF_201883171311570_CashFlow...</td>
          <td>상각후원가금융자산의 취득</td>
          <td>the acquisition of After-depreciation capital ...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>상각후원가금융자산의 취득</td>
          <td>None</td>
          <td>-158,716,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>21</th>
          <td>entity00126380_udf_CF_2018510204038291_CashFlo...</td>
          <td>기타포괄손익-공정가치금융자산의 처분</td>
          <td>Proceeds from disposal of fair value assessmen...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>기타포괄손익-공정가치금융자산의 처분</td>
          <td>None</td>
          <td>16,211,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>22</th>
          <td>entity00126380_udf_CF_2018510204040276_CashFlo...</td>
          <td>기타포괄손익-공정가치금융자산의 취득</td>
          <td>Proceeds from acquisition of fair value assess...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>기타포괄손익-공정가치금융자산의 취득</td>
          <td>None</td>
          <td>-456,134,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>23</th>
          <td>entity00126380_udf_CF_2018510204036276_CashFlo...</td>
          <td>당기손익-공정가치금융자산의 처분</td>
          <td>Proceeds from disposal of fair value assessmen...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>당기손익-공정가치금융자산의 처분</td>
          <td>None</td>
          <td>80,138,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>24</th>
          <td>entity00126380_udf_CF_2018510204025664_CashFlo...</td>
          <td>당기손익-공정가치금융자산의 취득</td>
          <td>Proceeds from acquisition of fair value assess...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>당기손익-공정가치금융자산의 취득</td>
          <td>None</td>
          <td>-193,848,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>25</th>
          <td>entity00126380_udf_CF_20171021101629105_CashFl...</td>
          <td>관계기업 및 공동기업 투자의 처분</td>
          <td>Proceeds from disposal of associates and joint...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>관계기업 및 공동기업 투자의 처분</td>
          <td>None</td>
          <td>148,000,000.0</td>
          <td>355,926,000,000.0</td>
          <td>2,280,203,000,000.0</td>
          <td>278,009,000,000.0</td>
          <td>2,014,430,000,000.0</td>
          <td>240,000,000.0</td>
          <td>41,091,000,000.0</td>
          <td>306,804,000,000.0</td>
          <td>277,907,000,000.0</td>
          <td>44,832,000,000.0</td>
        </tr>
        <tr>
          <th>26</th>
          <td>entity00126380_udf_CF_20171021101629633_CashFl...</td>
          <td>관계기업 및 공동기업 투자의 취득</td>
          <td>Acquisition from disposal of associates and jo...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>관계기업 및 공동기업 투자의 취득</td>
          <td>None</td>
          <td>-51,226,000,000.0</td>
          <td>-25,293,000,000.0</td>
          <td>-84,306,000,000.0</td>
          <td>-137,917,000,000.0</td>
          <td>-719,800,000,000.0</td>
          <td>-181,307,000,000.0</td>
          <td>-279,022,000,000.0</td>
          <td>-403,538,000,000.0</td>
          <td>-243,000,000.0</td>
          <td>-180,916,000,000.0</td>
        </tr>
        <tr>
          <th>27</th>
          <td>ifrs_ProceedsFromSalesOfPropertyPlantAndEquipm...</td>
          <td>유형자산의 처분</td>
          <td>Proceeds from sales of property, plant and equ...</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>유형자산의 처분</td>
          <td>None</td>
          <td>556,973,000,000.0</td>
          <td>308,354,000,000.0</td>
          <td>270,874,000,000.0</td>
          <td>357,154,000,000.0</td>
          <td>385,610,000,000.0</td>
          <td>377,445,000,000.0</td>
          <td>644,062,000,000.0</td>
          <td>379,878,000,000.0</td>
          <td>1,228,007,000,000.0</td>
          <td>100,899,000,000.0</td>
        </tr>
        <tr>
          <th>28</th>
          <td>ifrs_PurchaseOfPropertyPlantAndEquipmentClassi...</td>
          <td>유형자산의 취득</td>
          <td>Purchase of property, plant and equipment</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>유형자산의 취득</td>
          <td>None</td>
          <td>29,556,406,000,000.0</td>
          <td>42,792,234,000,000.0</td>
          <td>24,142,973,000,000.0</td>
          <td>-25,880,222,000,000.0</td>
          <td>-22,042,943,000,000.0</td>
          <td>-23,157,587,000,000.0</td>
          <td>-22,965,271,000,000.0</td>
          <td>-21,965,678,000,000.0</td>
          <td>-21,619,244,000,000.0</td>
          <td>-8,072,165,000,000.0</td>
        </tr>
        <tr>
          <th>29</th>
          <td>ifrs_ProceedsFromSalesOfIntangibleAssetsClassi...</td>
          <td>무형자산의 처분</td>
          <td>Proceeds from sales of intangible assets</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>무형자산의 처분</td>
          <td>None</td>
          <td>11,935,000,000.0</td>
          <td>733,000,000.0</td>
          <td>6,944,000,000.0</td>
          <td>1,083,000,000.0</td>
          <td>31,731,000,000.0</td>
          <td>4,562,000,000.0</td>
          <td>61,497,000,000.0</td>
          <td>9,703,000,000.0</td>
          <td>16,620,000,000.0</td>
          <td>56,795,000,000.0</td>
        </tr>
        <tr>
          <th>30</th>
          <td>ifrs_PurchaseOfIntangibleAssetsClassifiedAsInv...</td>
          <td>무형자산의 취득</td>
          <td>Purchase of intangible assets</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>무형자산의 취득</td>
          <td>None</td>
          <td>1,020,517,000,000.0</td>
          <td>983,740,000,000.0</td>
          <td>1,047,668,000,000.0</td>
          <td>-1,501,881,000,000.0</td>
          <td>-1,324,307,000,000.0</td>
          <td>-934,743,000,000.0</td>
          <td>-650,884,000,000.0</td>
          <td>-663,678,000,000.0</td>
          <td>-1,259,895,000,000.0</td>
          <td>-550,053,000,000.0</td>
        </tr>
        <tr>
          <th>31</th>
          <td>entity00126380_udf_CF_20171021101626447_CashFl...</td>
          <td>사업결합으로 인한 현금유출액</td>
          <td>Business combination</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>사업결합으로 인한 현금유출액</td>
          <td>None</td>
          <td>-99,108,000,000.0</td>
          <td>-8,754,268,000,000.0</td>
          <td>-622,050,000,000.0</td>
          <td>-411,445,000,000.0</td>
          <td>-176,625,000,000.0</td>
          <td>-167,155,000,000.0</td>
          <td>-464,279,000,000.0</td>
          <td>-522,740,000,000.0</td>
          <td>47,549,000,000.0</td>
          <td>290,218,000,000.0</td>
        </tr>
        <tr>
          <th>32</th>
          <td>entity00126380_udf_CF_20193111072555_CashFlows...</td>
          <td>사업양도로 인한 현금유입액</td>
          <td>Business sell</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>사업양도로 인한 현금유입액</td>
          <td>None</td>
          <td>nan</td>
          <td>1,248,834,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>925,454,000,000.0</td>
          <td>179,437,000,000.0</td>
          <td>0.0</td>
        </tr>
        <tr>
          <th>33</th>
          <td>entity00126380_udf_CF_20171021101625672_CashFl...</td>
          <td>현금의 기타유출입</td>
          <td>Others</td>
          <td>현금흐름표 [abstract]</td>
          <td>투자활동 현금흐름</td>
          <td>현금의 기타유출입</td>
          <td>None</td>
          <td>-2,289,000,000.0</td>
          <td>-28,455,000,000.0</td>
          <td>19,936,000,000.0</td>
          <td>421,231,000,000.0</td>
          <td>13,273,000,000.0</td>
          <td>29,715,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>34</th>
          <td>ifrs_CashFlowsFromUsedInFinancingActivities</td>
          <td>재무활동 현금흐름</td>
          <td>Cash flows from (used in) financing activities</td>
          <td>현금흐름표 [abstract]</td>
          <td>재무활동 현금흐름</td>
          <td>None</td>
          <td>None</td>
          <td>-15,090,222,000,000.0</td>
          <td>-12,560,867,000,000.0</td>
          <td>-8,669,514,000,000.0</td>
          <td>-6,573,509,000,000.0</td>
          <td>-3,057,109,000,000.0</td>
          <td>-4,137,031,000,000.0</td>
          <td>-1,864,508,000,000.0</td>
          <td>3,109,729,000,000.0</td>
          <td>-152,295,000,000.0</td>
          <td>-1,363,639,000,000.0</td>
        </tr>
        <tr>
          <th>35</th>
          <td>entity00126380_udf_CF_20171021102249949_CashFl...</td>
          <td>단기차입금의 순증가(감소)</td>
          <td>Net proceeds(repayment of) short-term borrowings</td>
          <td>현금흐름표 [abstract]</td>
          <td>재무활동 현금흐름</td>
          <td>단기차입금의 순증가(감소)</td>
          <td>None</td>
          <td>-2,046,470,000,000.0</td>
          <td>2,730,676,000,000.0</td>
          <td>1,351,037,000,000.0</td>
          <td>3,202,416,000,000.0</td>
          <td>1,833,419,000,000.0</td>
          <td>-1,861,536,000,000.0</td>
          <td>-800,579,000,000.0</td>
          <td>977,315,000,000.0</td>
          <td>868,156,000,000.0</td>
          <td>-533,298,000,000.0</td>
        </tr>
        <tr>
          <th>36</th>
          <td>dart_AcquisitionOfTreasuryShares</td>
          <td>자기주식의 취득</td>
          <td>Acquisition of treasury shares</td>
          <td>현금흐름표 [abstract]</td>
          <td>재무활동 현금흐름</td>
          <td>자기주식의 취득</td>
          <td>None</td>
          <td>875,111,000,000.0</td>
          <td>8,350,424,000,000.0</td>
          <td>7,707,938,000,000.0</td>
          <td>-5,015,112,000,000.0</td>
          <td>-1,125,322,000,000.0</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>37</th>
          <td>dart_ProceedsFromLongTermBorrowings</td>
          <td>사채 및 장기차입금의 차입</td>
          <td>Proceeds from long term borrowings</td>
          <td>현금흐름표 [abstract]</td>
          <td>재무활동 현금흐름</td>
          <td>사채 및 장기차입금의 차입</td>
          <td>None</td>
          <td>3,580,000,000.0</td>
          <td>998,311,000,000.0</td>
          <td>1,041,743,000,000.0</td>
          <td>192,474,000,000.0</td>
          <td>1,740,573,000,000.0</td>
          <td>26,672,000,000.0</td>
          <td>1,862,256,000,000.0</td>
          <td>3,925,406,000,000.0</td>
          <td>1,137,646,000,000.0</td>
          <td>311,500,000,000.0</td>
        </tr>
        <tr>
          <th>38</th>
          <td>dart_RepaymentsOfLongTermBorrowings</td>
          <td>사채 및 장기차입금의 상환</td>
          <td>Repayments of long term borrowings</td>
          <td>현금흐름표 [abstract]</td>
          <td>재무활동 현금흐름</td>
          <td>사채 및 장기차입금의 상환</td>
          <td>None</td>
          <td>1,986,597,000,000.0</td>
          <td>1,140,803,000,000.0</td>
          <td>252,846,000,000.0</td>
          <td>-1,801,465,000,000.0</td>
          <td>-3,299,595,000,000.0</td>
          <td>-1,368,436,000,000.0</td>
          <td>-522,899,000,000.0</td>
          <td>-1,145,167,000,000.0</td>
          <td>-304,074,000,000.0</td>
          <td>-400,562,000,000.0</td>
        </tr>
        <tr>
          <th>39</th>
          <td>ifrs_DividendsPaidClassifiedAsFinancingActivities</td>
          <td>배당금 지급</td>
          <td>Dividends paid</td>
          <td>현금흐름표 [abstract]</td>
          <td>재무활동 현금흐름</td>
          <td>배당금 지급</td>
          <td>None</td>
          <td>10,193,695,000,000.0</td>
          <td>6,804,297,000,000.0</td>
          <td>3,114,742,000,000.0</td>
          <td>-3,129,544,000,000.0</td>
          <td>-2,233,905,000,000.0</td>
          <td>-1,249,672,000,000.0</td>
          <td>-1,265,137,000,000.0</td>
          <td>-874,608,000,000.0</td>
          <td>-1,917,637,000,000.0</td>
          <td>-823,627,000,000.0</td>
        </tr>
        <tr>
          <th>40</th>
          <td>entity00126380_udf_CF_20171021102253395_CashFl...</td>
          <td>비지배지분의 증감</td>
          <td>Minority interests</td>
          <td>현금흐름표 [abstract]</td>
          <td>재무활동 현금흐름</td>
          <td>비지배지분의 증감</td>
          <td>None</td>
          <td>8,071,000,000.0</td>
          <td>5,670,000,000.0</td>
          <td>13,232,000,000.0</td>
          <td>-25,312,000,000.0</td>
          <td>139,000,000.0</td>
          <td>281,551,000,000.0</td>
          <td>-1,200,134,000,000.0</td>
          <td>363,417,000,000.0</td>
          <td>0.0</td>
          <td>nan</td>
        </tr>
        <tr>
          <th>41</th>
          <td>ifrs_EffectOfExchangeRateChangesOnCashAndCashE...</td>
          <td>외화환산으로 인한 현금의 변동</td>
          <td>Effect of exchange rate changes on cash and ca...</td>
          <td>현금흐름표 [abstract]</td>
          <td>외화환산으로 인한 현금의 변동</td>
          <td>None</td>
          <td>None</td>
          <td>94,187,000,000.0</td>
          <td>-1,782,270,000,000.0</td>
          <td>417,243,000,000.0</td>
          <td>-524,487,000,000.0</td>
          <td>-555,886,000,000.0</td>
          <td>-330,070,000,000.0</td>
          <td>-687,048,000,000.0</td>
          <td>-14,724,000,000.0</td>
          <td>-48,118,000,000.0</td>
          <td>263,995,000,000.0</td>
        </tr>
        <tr>
          <th>42</th>
          <td>ifrs_IncreaseDecreaseInCashAndCashEquivalents</td>
          <td>현금 및 현금성자산의 증가(감소)</td>
          <td>Net increase (decrease) in cash and cash equiv...</td>
          <td>현금흐름표 [abstract]</td>
          <td>현금 및 현금성자산의 증가(감소)</td>
          <td>None</td>
          <td>None</td>
          <td>-204,625,000,000.0</td>
          <td>-1,566,312,000,000.0</td>
          <td>9,474,698,000,000.0</td>
          <td>5,795,978,000,000.0</td>
          <td>555,986,000,000.0</td>
          <td>-2,506,680,000,000.0</td>
          <td>4,099,699,000,000.0</td>
          <td>4,900,342,000,000.0</td>
          <td>-358,511,000,000.0</td>
          <td>3,245,564,000,000.0</td>
        </tr>
        <tr>
          <th>43</th>
          <td>dart_CashAndCashEquivalentsAtBeginningOfPeriodCf</td>
          <td>기초 현금 및 현금성자산</td>
          <td>Cash and cash equivalents at beginning of period</td>
          <td>현금흐름표 [abstract]</td>
          <td>기초 현금 및 현금성자산</td>
          <td>None</td>
          <td>None</td>
          <td>30,545,130,000,000.0</td>
          <td>32,111,442,000,000.0</td>
          <td>22,636,744,000,000.0</td>
          <td>16,840,766,000,000.0</td>
          <td>16,284,780,000,000.0</td>
          <td>18,791,460,000,000.0</td>
          <td>14,691,761,000,000.0</td>
          <td>9,791,419,000,000.0</td>
          <td>10,149,930,000,000.0</td>
          <td>6,904,366,000,000.0</td>
        </tr>
        <tr>
          <th>44</th>
          <td>dart_CashAndCashEquivalentsAtEndOfPeriodCf</td>
          <td>기말 현금 및 현금성자산</td>
          <td>Cash and cash equivalents at end of period</td>
          <td>현금흐름표 [abstract]</td>
          <td>기말 현금 및 현금성자산</td>
          <td>None</td>
          <td>None</td>
          <td>30,340,505,000,000.0</td>
          <td>30,545,130,000,000.0</td>
          <td>32,111,442,000,000.0</td>
          <td>22,636,744,000,000.0</td>
          <td>16,840,766,000,000.0</td>
          <td>16,284,780,000,000.0</td>
          <td>18,791,460,000,000.0</td>
          <td>14,691,761,000,000.0</td>
          <td>9,791,419,000,000.0</td>
          <td>10,149,930,000,000.0</td>
        </tr>
      </tbody>
    </table>
    </div>



5 알려진버그
------------

-  재무제표 추출시 "전환일"이 있을 경우 Column Name이 변경되지 않는 버그
