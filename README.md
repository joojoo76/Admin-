<!DOCTYPE html>
<html lang="ko">
<head>
    <title>Admin Page</title>
    <!--부트스트랩 사용을 위한 코드 -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-4bw+/aepP/YC94hEpVNVgiZdgIC5+VKNBQNGCHeKRQN+PtmoHDEXuppvnDJzQIu9" crossorigin="anonymous">
</head>
<body>
    <div class="container mt-3">
        <h3 class="mt-5 mb-3">신규 등록 상품</h3>
        <form class="row row-cols-lg-auto g-3 align-items-center">      
            <div class="col-12">
              <label class="visually-hidden" for="inlineFormSelectPref">Preference</label>
              <select class="form-select" id="inlineFormSelectPref">
                <!-- 카테고리 셀렉트 코드를 넣어주세요-->
                    <option value="category">카테고리</option>
                    <option value="top">상의</option>
                    <option value="bottom">하의</option>
                    <option value="shose">신발</option>
                    <option value="goods">패션잡화</option>
              </select>
            </div>
            <div class="col-3">
                <!-- input 입력창 코드를 넣어주세요 -->
                <input type="text" class="form-control" placeholder="제품명을 입력해주세요">
            </div>
            <div class="col-auto">
                <!-- 조회라는 이름의 버튼 만들기 -->
                <button type="button" class="btn btn-primary">조회</button>
            </div>
          </form>
            <div class="container mt-3">
            <table class="table table-sm">
            <thead>
                <!-- 열의 속성값을 나타내는 코드를 작성해주세요 (예 : 카테고리, 브랜드, 상품명, 가격) -->
                <tr>
                    <th scope="col">카테고리</th>
                    <th scope="col">브랜드</th>
                    <th scope="col">상품명</th>
                    <th scope="col">가격</th>
                  </tr>            
            </thead>
            <tbody id="data-table">
                <!-- 추후 크롤링한 데이터가 들어가는 자리 -->
            </tbody>
            </table>
            </div>
                <!-- 페이지 네이션 코드를 넣어주세요 -->
            <nav aria-label="Page">
                    <ul class="pagination justify-content-center">
                    <li class="page-item disabled"><a class="page-link">Previous</a></li>
                    <li class="page-item"><a class="page-link" href="#">1</a></li>
                    <li class="page-item"><a class="page-link" href="#">2</a></li>
                    <li class="page-item"><a class="page-link" href="#">3</a></li>
                    <li class="page-item"><a class="page-link" href="#">Next</a>
            </nav>
    
    
   <script>
      // 크롤링한 데이터를 아래와 같은 형태의 객체 배열로 가정합니다.
      // 추후 데이터베이스에 있는 데이터를 쿼리문으로 불러 올 수 있게 쿼리르 작성해 볼 수 있음
      const data = [
          { category: "상의", brand: 'Supreme', product: '슈프림 박스로고 후드티', price: '390,000' },
          { category: "하의", brand: 'DIESEL', product: '디젤 트랙 팬츠', price: '188,000' },
          { category: "신발", brand: 'Nike', product: '에어포스 1', price: '137,000' },
          { category: "패션잡화", brand: 'Music&Goods', product: '빵빵이 키링', price: '29,000' },
          // ...
      ];
      
      const dataTable = document.getElementById('data-table');
      
      data.forEach((item) => {
          const row = dataTable.insertRow();
          row.insertCell(0).innerHTML = item.category;
          row.insertCell(1).innerHTML = item.brand;
          row.insertCell(2).innerHTML = item.product;
          row.insertCell(3).innerHTML = item.price;
      });
     

    </script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/js/bootstrap.bundle.min.js" integrity="sha384-HwwvtgBNo3bZJJLYd8oVXjrBZt8cqVSpeBNS5n7C8IVInixGAoxmnlMuBnhbgrkm" crossorigin="anonymous"></script>
</body>
	</html>
