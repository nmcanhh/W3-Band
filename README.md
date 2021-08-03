# 1. Header
Tạo `index.html`, `assets/css/style.css`, `assets/img`

0) Tạo khung HTML
	
	<div id="main">
	    <div id="header">
	      <ul id="nav">
	        <li><a href="">Home</a></li>
	        <li><a href="">Band</a></li>
	        <li><a href="">Tour</a></li>
	        <li><a href="">Contact</a></li>
	        <li>
	          <a href="">More</a>
	          <ul class="subnav">
	            <li><a href="">Merchandise</a></li>
	            <li><a href="">Extras</a></li>
	            <li><a href="">Media</a></li>
	          </ul>
	        </li>
	      </ul>
	    </div>
	
	    <div id="slider">
	    </div>
	
	    <div id="content">
	    </div>
	    
	    <div id="footer">
	    </div>
	    
  	</div>
	
1) Tạo `Reset CSS`

	* {
	  padding: 0;
	  margin: 0;
	  box-sizing: border-box;
	}

2) Tạo CSS cho `#header`

	#header {
	  height: 46px; 
	  background-color: #000;
	}

3) Tạo CSS cho `#nav li`

	#nav li {
	  display: inline-block;
	}

Thẻ `li` có thuộc tính mặc định là `display: list-item` nên tất cả content sẽ được xổ dọc xuống, ta có thể đổi thành `inline-block` để nó xổ ngang. `inline` là đứng trên 1 hàng, `block` là giữ lại tính chất khối để đặt được kích thước.

4) Ẩn `subnav` của More đi

	#nav .subnav {
	  display: none;
	}

5) Set chữ màu trắng, ẩn đường gạch chân của thẻ `a`

	#nav li a {
	  color: #fff;
	  text-decoration: none;
	}

6) Căn giữa chiều cao cho thẻ `#nav li a`

	#nav li a {
  		line-height: 46px;
	}

Chữ luôn nằm giữa chiều cao của chính nó, ví dụ như thẻ `a` không có kích thước chiều cao bằng với thẻ `div` bao bọc nó thì mình cho `line-height` của thẻ `a` bằng với `chiều cao` của thẻ `div`, khi đó chữ sẽ được căn giữa chiều cao.

7) Tăng độ giãn cách nhau cho thẻ `a`

	#nav li a {
	  padding: 0 24px;
	}

8) Đổi font cho toàn bộ trang web

	html {
	  font-family: Arial, Helvetica, sans-serif;
	}

9) Thêm hiệu ứng khi rê vào thẻ `a` 

	#nav li:hover a {
	  color: #000;
	  background-color: #ccc;
	}

Theo kinh nghiệm, chúng ta thêm hover cho thẻ `li` chứ không thêm vào thẻ `a`, vẫn có tác dụng như bình thường.

10) Thay đổi kích thước chiều ngang và chiều dọc của thẻ `a`, khi đó hover cũng sẽ full viền.

	#nav li a {
	  display: inline-block;
	}

Tính chất mặc định của thẻ `a` là inline, không set được kích thước chiều ngang và chiều dọc. Vậy nên ta phải thêm `display: inline-block` để set được chiều ngang và chiều dọc. Sau đó thẻ a sẽ thừa kế thêm `line-height` của nó.

11) Set background tạm thời cho `#slider` để dễ nhìn

	#slider {
	  min-height: 500px;
	  background-color: #333;
	}

12) Hiện `subnav` của More

	#nav .subnav {
	  display: block;
	}

13) Cho thẻ cha `li` có thuộc tính là `relative`

	#nav li {
	  position: relative;
	}

14) Cho thẻ con `ul` có thuộc tính là `absolute`

	#nav .subnav {
	  position: absolute;
	}

15) Cho khối `#subnav` có màu trắng

	#nav .subnav {
	  background-color: #fff;
	}

Lúc này, chứ trong khối `#subnav` cũng màu trắng vì thuộc tính `color: #fff` đã áp dụng lên cho thẻ  `a` cấp 1 và cấp 2.

16) Thay đổi phạm vi áp dụng `color: #fff` trực tiếp lên thẻ `a` cấp 1 

	#nav > li > a {
	  color: #fff;
	}
	
	#nav li a {
	  // color: #fff; (5) 
	}

18) Lúc này chữ của thẻ `a` cấp 2 sẽ thành màu tím, chúng ta cho màu thành `color: #000`

	#nav .subnav a {
	  color: #000;
	}
	
19) Thay đổi phạm vi áp dụng `background-color: #ccc;` khi hover trực tiếp lên thẻ `a` cấp 1

	#nav > li:hover > a {
	  background-color: #ccc; 
	}  

20) Thêm thuộc tính khi hover thẻ `a` của `#subnav`

	#nav .subnav li:hover a {
	  color: #000;
	  background-color: #ccc;
	}


21) Lúc này khi hover vào thẻ a của `#subnav` thì phần hover sẽ không bao hết chiều ngang. Lý do là ở thẻ a cấp 2 (lúc này thuộc tính trong `#nav li a` đã áp dụng lên cho cả thẻ a cấp 1 và cấp 2) đang để là `display: inline-block`,nó sẽ set được chiều ngang và chiều dọc nhưng sẽ không kế thừa được chiều rộng của thẻ chứa nó, tức là thẻ `li`. Ta đổi thành `display: block` để giải quyết vấn đề này. 

	#nav li a {
	  display: block;
	}

22) Lúc này thuộc tính trong thẻ `#nav li` sẽ áp dụng lên cả thẻ `li` cấp 1 và cấp 2, vô tình, thẻ a cấp 2 sẽ thừa kế chiều rộng được tạo bằng thuộc tính `display: inline-block` của thẻ `li` cấp 2, để thuộc tính này chỉ áp dụng lên thẻ `li` cấp 1, ta thay đổi phạm vi áp dụng thuộc tính trên.

	#nav li {
	  /* display: inline-block; */
	}

	#nav > li {
	  display: inline-block;
	}

23) Bỏ thuộc tính dấu chấm của thẻ `ul` cấp 1 và 2

	#nav, .subnav {
	  list-style-type: none;
	}

24) UpperCase thẻ a cấp 1

	#nav > li > a {
	  text-transform: uppercase;
	}

 
25) Giảm `padding` `left`, `right` của thẻ `a` cấp 2

	#nav .subnav a {
	  padding: 0 16px;
	}

26) Thay đổi `line-height` của thẻ a cấp 2 `#subnav`

	#nav .subnav a {
	  line-height: 38px;
	}
	
27) Ẩn đi nền đen của `#slider`

	#slider {
	  /* min-height: 500px;
	  background-color: #333; */
	}

28) Thêm bóng đổ cho `#subnav`

	#nav .subnav {
	  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
	}

29) Ẩn đi `#subnav`

	#nav .subnav {
	  display: none;
	}

29a) Hover vào thẻ `li` chứa `More` thì hiện thẻ `ul` `#subnav` con của `li`

	#nav li:hover .subnav {
	  display: block;
	}

30) Trong một số trường hợp, một số trình duyệt sẽ không hiển thị đúng vị trí của `#subnav`, để giải quyết vấn đề này, chúng ta set vị trí cho `#subnav` luôn, mặc dù `position: absolute` đã giải quyết được vấn đề này.

	#nav .subnav {
	  top: 100%;
	  left: 0;
	}

Tải Themify Icons tại `https://themify.me/themify-icons`, sau đỏ giải nén và cho thư mục Themify vào `assets/fonts`, nhúng font bằng `<link rel="stylesheet" href="./assets/fonts/themify-icons/themify-icons.css">`

31) Thêm `arrow` icon vào `More` và đặt tên class cho nó là `nav-arrow-down`

	<a href="">More
	  <i class="nav-arrow-down ti-angle-down"></i>
	</a> 

32) Thay đổi kích thước của `nav-arrow-down`

	#nav .nav-arrow-down {
	  font-size: 14px;
	}

33) Thêm Search button

	<div class="search-btn">
		<i class="search-icon ti-search"></i>
	</div> 

34) Thay đổi màu sắc và kích thước của `search-icon` 

	#header .search-icon {
	  color: #fff;
	  font-size: 14px;
	}

35) Lúc này, thẻ `ul` chứa Navigation sẽ chiếm toàn bộ chiều ngang, chúng ta phải làm cho Navigation có nội dung đến đâu thì có chiều dài đến đấy. Sử dụng `inline-block` cho `#nav`

	#nav {
	  display: inline-block;
	}

36) Lúc này, thẻ `div` chứa `search-btn` cũng đang chiếm hết chiều ngang của thẻ cha là `#header`, vì quá dài nên không chui lên được thẻ `#header`. Chúng ta sử dụng `float: right` để kéo thẻ `div` sang bên phải, khi một thẻ div dù có kế thừa chiều ngang thì sử dụng dụng `float` thì sẽ mất tính chất kế thừa chiều ngang.

	#header .search-btn {
	  float: right;
	}

37) Căn giữa chiều cao cho `search-icon` bằng cách sử dụng `line-height`

	#header .search-icon {
	  line-height: 46px;
	}
	
38) Căn giữa chiều ngang cho `search-btn` bằng cách sử dụng `padding`

	#header .search-btn:hover {
	  background-color: #f44336;
	}

39) Thay style trỏ chuột khi hover 

	#header .search-btn:hover {
	  cursor: pointer;
	}

40) Tăng chiều cao và set màu cho `#content` 

	#content {
	  height: 1000px;
	  background-color: #ccc;
	}

41) Bám dính `#header` vào bên trên trình duyệt

	#header {
	  position: fixed;
	  top: 0;
	  left: 0;
	  right: 0;
	}
	
với `position: fixed` nổi lên trên, `top: 0` dính sát mép bên trên, `left: 0` dính sát mép bên trái và `right: 0` dính sát mép bên phải.

42) Tăng chiều cao và màu cho `#slider`

	#slider {
	  height: 400px;
	  background-color: green;
	}

43) Lúc này, chúng ta select `#slider` thì nó chọn luôn phần của `#header`. Lý do là `#header` sử dụng `position: fixed;`, nó sẽ nổi lên 1 tầng cao hơn và nhường vị trí đấy cho `#slider`, tức là `#header` đang đè lên trên `#slider`. Chúng ta mong muốn là phần `#content` sẽ nằm bên dưới mép của `#slider`. Vậy nên chúng ta sẽ sử dụng `margin-top` bằng với chiều cao của `#header`, tức là `#slider` sẽ bắt đầu từ vị trí `46px` của `#header`.
	
	#slider {
	  margin-top: 46px;
	}
	
44) Xóa màu và chiều cao của `#slider`

	#slider {
	  // height: 400px;
	  // background-color: green;
	}

# 2. Slider

Cứ có ông này đè lên ông kia thì sử dụng thuộc tính `position`.

Thẻ div mặc định là chiếm hết chiều ngang của trình duyệt.

Tự lưu hình vào `assets/img/slider`

45) Đặt `#slider` có kích thước chiều cao bằng 50% kích thước chiều ngang.

	#slider {
	  padding-top: 50%;
	}

Khi giá trị của thuộc tính padding-top là pixel thì không nói, nhưng khi là % thì nó là phần trăm của chiều ngang chính nó.

46) Sử dụng `background-image` cho `#slider`, `background-image` nó sẽ đổ nền ảnh tính từ phần padding. 

	#slider {
	  background: url("/assets/img/slider/slider1.jpeg") top center / cover no-repeat;
	}

với `top` là lấy phần trên, `center` là lấy giữa, `cover` là kiểu kích thước và `no-repeat` là không lặp lại.

47) Thêm `text-content`

    <div id="slider">
      <div class="text-content">
        <h2 class="text-heading">New York</h2>
        <p>The atmosphere in New York is lorem ipsum.</p>
      </div>
    </div>

48) Thay đổi màu chữ của `#text-content`

	#slider .text-content {
	  color: #fff;
	}

49) Sử dụng `position: relative` cho `#slider` và `position: absolute` cho phần text. Lúc này, phần text sẽ được nổi lên 1 lớp so với `#slider`.	

	#slider {
	  position: relative;
	}

	#slider .text-content {
	  position: absolute;
	}

50) Chỉnh vị trí từ đáy #slider đến text-content

	#slider .text-content {
	  bottom: 47px;
	}

51) Căn giữa text-content

	#slider .text-content {
	  left: 50%;
	  transform: translateX(-50%);
	  text-align: center;
	}

Có thể thay `transform: translateX(-50%)`, `text-align: center` bằng `width: 100%` hoặc thay bằng `left: 0`, `right: 0`

52) Giảm độ giày thẻ `#text-heading`

	#slider .text-heading {
	  font-weight: 500;
	}

giá trị của `font-weight` giao động từ 100 đến 700

53) Thay đổi cỡ chữ cho `#text-heading` và `#text-description`

	#slider .text-heading {
	  font-size: 24px;
	}
	
	#slider .text-description {
	  font-size: 15px;
	}

54) Thay đổi khoảng cách từ `#text-description` lên `#text-heading`
	
	#slider .text-description {
	  margin-top: 25px;
	}

55) Fix lỗi khi lăn chuột xuống dưới thì slider che mất thanh header.

	#header {
	  z-index: 1;
	}

# 3. About section

56) Xóa đi CSS của `#content`

57) Thêm `#content-section` cho About

<!-- About section -->
	<div class="content-section">
		<h2 class="section-heading">THE BAND</h2>
		<p class="section-sub-heading">We love music</p>
		<p class="about-text">We have created a fictional band website. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      </div>
	</div>

58) Set kích thước cho `.content-section`

	#content .content-section {
	  width: 800px;
	}

59) Căn `.content-section` ra giữa website

	#content .content-section {
	  margin-left: auto;
	  margin-right: auto;
	}
	
60) Căn dọc cho `.content-section`

	#content .content-section {
	  padding: 64px 0;
	}

61) Căn giữa `.section-heading`, `.section-sub-heading`

	#content .section-heading {
	  text-align: center;
	}
	
	#content .section-sub-heading {
	  text-align: center;
	}

62) Thay đổi font-size cho `.section-heading`, `.section-sub-heading`

	#content .section-heading {
	  font-size: 30px;
	}
	
	#content .section-sub-heading {
	  font-size: 15px;
	}
	
63) Làm mỏng font chữ của `.section-heading`

	#content .section-heading {
	  font-weight: 500;
	}
	
64) Làm giãn đều chữ của `.section-heading`

	#content .section-heading {
	  letter-spacing: 4px;
	}

65) Thay đổi khoảng cách từ `.section-sub-heading` lên `.section-heading`
	
	#content .section-sub-heading  {
	  margin-top: 25px;
	}
	
66) Thay đổi khoảng cách từ `.about-text` lên `.section-sub-heading` và font-size của `.about-text`.
	
	#content .about-text {
  		margin-top: 25px;
  		font-size: 15px;
	}

67) Set chữ nghiêng cho `.section-sub-heading`

	#content .section-sub-heading {
	  font-style: italic;
	}
	
68) Set chữ mờ cho `.section-sub-heading`

	#content .section-sub-heading {
		  opacity: 0.6;
		}

69) Làm phẳng chữ 2 bên cho `.about-text`.

	#content .about-text {
	  text-align: justify;
	}
	
70) Thay đổi khoảng cách giữa 2 dòng của `.about-text`.

	#content .about-text {
	  line-height: 1.4;
	}

Chiều cao của 1 dòng thì sử dụng `line-height`. Với Tiếng Anh là 1.4 và Tiếng Việt là 1.6

71) Thêm Tour section

	<!-- Tour section -->
		<div class="content-section">
		<h2 class="section-heading">TOUR DATES</h2>
		<p class="section-sub-heading">Remember to book your tickets!</p>
	</div>


72) Thêm Contact section

	<!-- Contact section -->
	<div class="content-section">
		<h2 class="section-heading">CONTACT</h2>
		<p class="section-sub-heading">Fan? Drop a note!</p>
	</div>
	
Tự lưu hình vào `assets/img/band`

73) Thêm `member-list`

	  <div class="content-section">
	    <div class="member-list">
	      <div class="member-item">
	        <p class="member-name">Name</p>
	        <img src="./assets/img/band/member1.jpeg" alt="Name" class="member-img">
	      </div>
	      <div class="member-item"> 
	        <p class="member-name">Name</p>
	        <img src="./assets/img/band/member1.jpeg" alt="Name" class="member-img">
	      </div>
	      <div class="member-item">
	        <p class="member-name">Name</p>
	        <img src="./assets/img/band/member1.jpeg" alt="Name" class="member-img">
	      </div>
	    </div>
  </div>
  
74) Set 3 `.member-item` đứng chung 1 hàng

	#content .member-item {
	  float: left;
	}

75) Thay đổi khoảng cách từ `.member-list` đến `.about-text`

	#content .member-list {
	  margin-top: 48px;
	}

76) Chia đều `.member-list` thành 3 phần, tức là mỗi `.member-item` chiếm 33.33333%

	#content .member-item {
	  width: 33.33333%;
	}

Có thể sử dụng hàm để chia thành 33.33333% bằng `calc(100% / 3)`

77) Căn giữa `.member-list`

	#content .member-list {
	  text-align: center;
	}
	
78) Thay đổi khoảng cách từ `.member-img` đến `.member-name`

	#content .member-img {
	  margin-top: 15px;
	}

79) Thay đổi kích thước chiều ngang của `.member-img`

	#content .member-img {
	  width: 154px;
	}

80) Bo tròn `.member-img`

	#content .member-img {
	  border-radius: 4px;
	}

81) Khi ta select element `.member-list` thì trình duyệt không select toàn bộ 3 `.member-item` mà chỉ select 1 lớp nhỏ không liên quan. Đây là 1 lỗi khi sử dụng `float`. Nếu các thẻ con bên trong 1 thẻ cha sử dụng `float` thì thẻ cha bên ngoài sẽ bị co lại. Để khắc phục, chúng ta thêm 1 class là con của class cha `.member-list` có tên là clear. 

	<div class="clear"></div>	
	
Phía CSS chúng ta set:

	.clear {
	  clear: both;
	}

Hoặc chúng ta thêm  `overflow: hidden` vào thẻ cha `.member-list`.

# 4. Tour tickets

82) Khi đổ nền đen, chúng ta chỉ đổ được nền ở Content, Padding nhưng không đổ được Margin. Để giải quyết, chúng ta tạo 1 thẻ `div` cha cho `content-section` và để nền đen cho thẻ `div` có tên là `tour-section`

	  <div class="tour-section">
	    <div class="content-section">
	      <h2 class="section-heading">TOUR DATES</h2>
	      <p class="section-sub-heading">Remember to book your tickets!</p>
	    </div>
	  </div>


CSS:

	.tour-section {
	  background-color: #000;
	}

83) Tạo class chữ màu trắng để sau này dùng lại nhiều lần.

	.text-white {
		color: #fff !important;
	}

Dùng important khi class đó chỉ có 1 chức năng. Nếu dùng linh tinh rất khó kiểm soát.

84) Set chữ màu trắng cho `.section-heading` và `.section-sub-heading` bằng cách thêm class `text-white`

	<h2 class="section-heading text-white">TOUR DATES</h2>
	<p class="section-sub-heading text-white">Remember to book your tickets!</p>
	
85) Thêm thẻ ul chứa danh sách các đợt vé và `background-color` màu trắng cho nó.

	<ul class="ticket-list">
		<li>September <span class="sold-out">Sold out</span></li>
	    <li>October <span class="sold-out">Sold out</span></li>
	    <li>November <span class="quantity">3</span></li>
	 </ul> 

CSS:

	.ticket-list {
	  background-color: #fff;
	}

86) Thay đổi khoảng cách từ `.ticket-list` đến `.section-sub-heading`

	.ticket-list {
	  margin-top: 40px;
	}
	
87) Thay đổi cỡ chữ của thẻ `.ticket-list li`

	.ticket-list li {
	  font-size: 15px;
	}

88) Căn đều ngang dọc cho thẻ `.ticket-list li`

	.ticket-list li {
	  padding: 11px 16px;
	}

89) Tạo `border-bottom` cho `.ticket-list li`

	.ticket-list li {
	  border-bottom: 1px solid #ddd;
	}

90) Thay đổi màu chữ cho `.ticket-list li` 

	.ticket-list li {
	  color: #757575;
	}

91) Thêm màu nên và màu chữ cho `.ticket-list .sold-out`

	.ticket-list .sold-out {
	  background-color: #f44336;
	  color: #fff;
	}

92) Padding cho `.ticket-list .sold-out`
	
	.ticket-list .sold-out {
	  padding: 3px 4px;
	}

93) Vị trí của `.ticket-list .sold-out` 

	.ticket-list .sold-out {
	  margin-left: 16px;
	}

94) Di chuyển `.ticket-list .quantity` sang phải

	.ticket-list .quantity {
	  float: right;
	}

95) Set chiều rộng, cao, màu nền và màu chữ cho `.ticket-list .quantity`
	
	.ticket-list .quantity {
	  width: 24px;
	  height: 24px;
	  background-color: #000;
	  color: #fff;
	}

96) Set bo tròn cho `.ticket-list .quantity`

	.ticket-list .quantity {
	  border-radius: 50%;
	 }

97) Căn giữa, căn dọc cho `.ticket-list .quantity`

	.ticket-list .quantity {
	  text-align: center;
	  line-height: 24px;
	}

98) `.ticket-list .quantity` vẫn cảm thấy bị lệch, chúng ta sử dụng `margin` âm

	.ticket-list .quantity {
	  margin-top: -3px;
	}

Để sử dụng `margin` âm thì class phải sử dụng `float` 

1 thẻ đang có `inline` mà thêm `float` thì thẻ đó thành `block`. Khi có `block` rồi thì set được `width`, `height`

99) Bỏ dấu chấm của `.ticket-list li`

	.ticket-list li {
	  list-style-type: none;
	}

Lưu hình địa điểm lưu trong `assets/img/places`

100) Thêm `.place-list` và `place-item`

	<!-- Places -->
	  <div class="place-list">
	    <div class="place-item">
	      <img src="./assets/img/places/place1.jpeg" alt="New York" class="place-img">
	      <div class="place-body">
	        <h3 class="place-heading">New York</h3>
	        <p class="place-time">Fri 27 Nov 2016</p>
	        <p class="place-dsc">Praesent tincidunt sed tellus ut rutrum sed vitae justo.<p>
	        <a href="#" class="place-buy-btn">Buy Tickets</a>
	      </div>
	    </div>
	    <div class="place-item">
	      <img src="./assets/img/places/place1.jpeg" alt="New York" class="place-img">
	      <div class="place-body">
	        <h3 class="place-heading">New York</h3>
	        <p class="place-time">Fri 27 Nov 2016</p>
	        <p class="place-dsc">Praesent tincidunt sed tellus ut rutrum sed vitae justo.<p>
	        <a href="#" class="place-buy-btn">Buy Tickets</a>
	      </div>
	    </div>
	    <div class="place-item">
	      <img src="./assets/img/places/place1.jpeg" alt="New York" class="place-img">
	      <div class="place-body">
	        <h3 class="place-heading">New York</h3>
	        <p class="place-time">Fri 27 Nov 2016</p>
	        <p class="place-dsc">Praesent tincidunt sed tellus ut rutrum sed vitae justo.<p>
	        <a href="#" class="place-buy-btn">Buy Tickets</a>
	      </div>
	    </div>
	  </div>
	  
100) Thay đổi khoảng cách từ `.place-list` đến `.ticket-list`

	.place-list {
	  margin-top: 32px;
	}

101) Dàn phải cho `.place-item`

	.place-item {
	  float: left;
	  width: 33.333333%;
	}

102) Lúc này, kích thước thẻ `img` là 400, to hơn thẻ chứa nó là `.place-item` nên `img` đã phìn ra.

Chúng ta đi set `width: 100%` cho img thì sẽ fix được lỗi này.

	.place-img {
	  width: 100%;
	}

103) Tạo ra khoảng cách giữa các `.place-item`

	.place-item {
	  padding: 0 8px;
	}

104) Fix lỗi không ôm hết các element của `.place-list` bằng cách sử dùng class `.clear`

	<div class="clear"></div>

105) Hiện tại, `.place-item` 1 và 3 bị thụt vào trong, chúng ta cần `.place-item` 1 và 3 thẳng mép. Ta áp dụng kỹ thuật `margin` âm vào thẻ chứa các `.place-item`.

	.place-list {
	  margin-left: -8px;
	  margin-right: -8px;
	} 

106) Hiệu ứng khi hover vào `img`

	.place-img:hover {
	  opacity: 0.6;
	}

107) Tạo màu nền cho `.place-body`

	.place-body {
	  background-color: #fff;
	}

108) `.img` đang có thuộc tính inline, `.place-body` đang có thuộc tính là block. Khi 2 ông này chồng lên nhau thì tạo ra 1 khoảng màu đen. Cách khắc phục là mình biến `.img` có thuộc tính là block.

	.place-img {
	  display: block;
	}

109) Padding 4 hướng cho `.place-body`

	.place-body {
	  padding: 16px;
	}
	
110) Set kích thước font cho `.place-body` và `.place-heading`

	.place-body {
	  font-size: 15px;
	}
		
	.place-heading {
	  font-size: 15px;
	  font-weight: 600;
	}

111) Tạo khoảng cách giữa `.place-time` và `.place-heading`

	.place-time {
	  margin-top: 15px;
	}

112) Thay màu chữ cho `.place-time`

	.place-time {
	  color: #757575;
	}

112a) Tạo khoảng cách giữa `.place-dsc` và `.place-time`

	.place-dsc {
	  margin-top: 15px;
	}

113) Chỉnh khoảng cách giữa các dòng của `.place-dsc`

	.place-dsc {
	  line-height: 1.4;
	}

114) Chỉnh màu chữ, màu nền, bỏ gạch chân, padding cho `.place-buy-btn`

	.place-buy-btn {
	  color: #fff;
	  background-color: #000;
	  text-decoration: none;
	  padding: 11px 16px;
	}

115) Cho thuộc tính `inline` của `.place-buy-btn` thành `inline-block`

	.place-buy-btn {
	  display: inline-block;
	}

116) Thay đổi khoảng cách từ `.place-buy-btn` đến `.place-dsc`

	.place-buy-btn {
	  margin-top: 15px;
	}

117) Thêm hover cho `.place-buy-btn`

	.place-buy-btn:hover {
	  color: #000;
	  background-color: #ccc;
	}

118) Padding dưới đáy cho `.place-list `

	.place-list {
	  padding-bottom: 48px;
	}

# 5. Modal

119) Tạo lớp Modal

	<div class="modal">
	</div>
	
CSS:

	.modal {
	  position: fixed;
	  top: 0;
	  bottom: 0;
	  left: 0;
	  right: 0;
	  background: rgba(0, 0, 0, 0.4);
	}
	
4 hướng bằng 0 cùng với `position: fixed` thì tạo ra 1 lớp phủ kín.

120) Thêm các icon, label ... vào modal

	 <div class="modal">
    <div class="modal-container">
      <div class="modal-close">
        <i class="modal-heading-icon ti-close"></i>
      </div>

      <header class="modal-header">
        <ti class="ti-bag"></ti>
        Tickets
      </header>

      <div class="modal-body">
        <label for="" class="modal-label">
          <i class="ti-shopping-cart"></i>
          Tickets, $15 per person
        </label>
        <input type="text" class="modal-input" placeholder="How many?">

        <label for="" class="modal-label">
          <i class="ti-user"></i>
           Send To
        </label>
        <input type="email" class="modal-input" placeholder="Enter email">

        <button id="buy-tickets">
          Pay <i class="ti-check"></i>
        </button>
      </div>

      <footer class="modal-footer">
        <p class="modal-help">Need <a href="#">help?</a></p>
      </footer>

    </div>
  </div> 
	  
121) Căn `.modal-container` ra giữa màn hình bằng cách thêm vào thẻ cha chứa `.modal`

Sử dụng flexbox, biến `.modal` thành `display: flex`. Tại `.modal` thêm `align-items: center`, lúc này `.modal-container` sẽ nào giữa chiều cao của `.modal`. Tiếp tục thêm `justify-content: center` và `.modal` để `.modal-container` nằm giữa chiều ngang của `.modal`

	.modal {
	  display: flex;
	  align-items: center;
	  justify-content: center;
	}

122) Thêm màu nền cho `.modal-container` 

	.modal .modal-container {
	  background-color: #fff;
	}

123) Thay đổi kích thước cho `.modal-container` 

	.modal .modal-container {
	  width: 900px;
	  min-height: 200px;
	}

Để `min-height` để khi content nhiều thì nó sẽ dãn ra theo chiều cao.

124) Set màu nền và chiều cao cho `.modal-header` vì chiều rộng đã được set sẵn ở `.modal` rồi.

	.modal-header {
	  background: #009688;
	  height: 130px;
	}

125) Căn giữa, set font-size và màu cho `Tickets`

	.modal-header {
	  display: flex;
	  align-items: center;
	  justify-content: center;
	  font-size: 30px;
	  color: #fff;
	}

126) Cho `.modal-heading-icon` dịch sang phải

	.modal-heading-icon {
	  margin-right: 16px;
	}

127) Thêm thuộc tính relative và absolute vào `.modal .modal-container` và `.modal-close` để `.modal-close` nằm trong `.modal .modal-container`

	.modal .modal-container {
	  position: relative;
	}
	
	.modal-close {
	  position: absolute;
	}

128) Cho `.modal-close` dịch lên trên và sang trái

	.modal-close {
	  top: 0;
	  right: 0;
	}

129) Set màu chữ, padding, opacity cho `.modal-close`

	.modal-close {
	  color: #fff;
	  padding: 12px;
	  opacity: 0.8;
	}

Lý do chúng ta không sử dụng top, right để kéo dấu close vào trong mà dùng padding là vì khi dùng padding, chúng ta sẽ chọn được 1 vùng lớn khi nhấn vào. Còn khi dùng top, right thì chỉ click vào đúng icon thì mới chạy.

130) Thêm hover cho `.modal-close`

	.modal-close:hover {
	  opacity: 1;
	  cursor: pointer;
	}

131) Lùi `.modal-body` vào trong

	.modal-body {
	  padding: 16px;
	}
	
132) Input và label đang nằm trên cùng 1 hàng, nó đang có dạng `display: inline-block` là nằm trên cùng 1 hàng. Bây giờ chúng ta chuyển thành `display: block` vào input hoặc label để input và label nằm mỗi hàng riêng biệt. Đồng thời đổi font-size.

	.modal-label {
	  display: block;
	  font-size: 15px;
	}

133) Thay đổi kích thước ô input, chúng ta sử dụng padding. Để sau này nếu thay đổi font chữ thì ô input sẽ  tự cao theo. Đồng thời set độ rộng 100%, thay đổi font chữ và border cho input.

	.modal-input {
	  font-size: 15px;
	  border: 1px solid #ccc;
	  width: 100%;
	  padding: 10px;
	}
	 
134) Thay đổi khoảng cách từ label xuống ô input

	.modal-label {
	  margin-bottom: 12px;
	}

135) Thay đổi khoảng cách từ input xuống label

	.modal-input {
	  margin-bottom: 24px;
	}

136) Đặt cho thẻ input 1 id và truyền id đó vào thuộc tính  for="" của label. Khi click vào label thì sẽ tự động focus vào input.

	<label for="ticket-quantity" class="modal-label">
		<i class="ti-shopping-cart"></i>
	   Tickets, $15 per person
	</label>
	<input id="ticket-quantity" type="text" class="modal-input" placeholder="How many?">
	
137) Thêm màu nền, màu chữ, độ rộng, cỡ chữ, thay đổi border, kiểu chữ và độ rộng cho `#buy-tickets`

	#buy-tickets {
	  background-color: #009688;
	  color: #fff;
	  width: 100%;
	  font-size: 15px;
	  border: none;
	  text-transform: uppercase;
	  padding: 18px;
	}

138) Thêm hover cho `#buy-tickets`

	#buy-tickets:hover {
	  opacity: 0.9;
	  cursor: pointer;
	} 
	
139) Tăng độ rộng của Footer và cho nằm sang phải

	.modal-footer {
	  padding: 16px;
	  text-align: right;
	}

140) Chỉnh màu chữ cho `.modal-footer a`

	.modal-footer a {
	  color: #2196f3;
	}

141) Reponsive cho `.modal`

	.modal .modal-container {
	  max-width: calc(100% - 32px);
	}

width sẽ luôn cách mỗi bên là `11px` khi chúng ta co lại.

142) Thêm `.modal.open` 

	.modal.open {
	  display: flex;
	}

143) Tại `.modal`, đổi `display: flex` thành `.display: none`

	.modal {
	  display: none;
	}

144) Thêm một số class JS

	<div class="modal js-modal">
	    <div class="modal-container js-modal-container">
	      <div class="modal-close js-modal-close">
	
	<button class="place-buy-btn js-buy-ticket">Buy Tickets</button>
	
145) Thêm Javascript

    const buyBtns = document.querySelectorAll('.js-buy-ticket');
    const modal = document.querySelector('.js-modal');
    const modalClose = document.querySelector('.js-modal-close');
    const modalContainer = document.querySelector('.js-modal-container');

    function showBuyTickets() {
      modal.classList.add('modal-open');
    }

    function hideBuyTickets() {
      modal.classList.remove('modal-open');
    }
    for (const buyBtn of buyBtns) {
      buyBtn.addEventListener('click', showBuyTickets);
    }

    modalClose.addEventListener('click', hideBuyTickets);

    modal.addEventListener('click', hideBuyTickets);

    modalContainer.addEventListener('click', function(event) {
      event.stopPropagation();
    });
   
146) Thêm một số hiệu ứng chuyển động

	@keyframes modalFadeIn {
	  from {
	    opacity: 0;
	    transform: translateY(-140px);
	  }
	  to {
	    opacty: 1;
	    transform: translateY(0);
	  }
	}

147) Thêm thuộc tính `animation` cho `.modal .modal-container`

	.modal .modal-container {
	  animation: modalFadeIn ease 0.3s;
	}

# 6. Row - columns layout
Tạo các class chung gồm `row` và `column`

148) Tạo `.row`

	.row {
	  margin-left: -8px;
	  margin-right: -8px;
	}

149) Ẩn `margin-left` và `margin-right` ở `.place-list`

	.place-list {
	  // margin-left: -8px;
	  // margin-right: -8px; 
	}

150) Thêm vào `<div class="place-list">` class `.row`

	<div class="row place-list">

151) Tạo `.col`

	.col {
	  float: left;
	  padding-left: 8px;
	  padding-right: 8px;
	}

152) Ẩn `float`, `padding-left` và `padding-left` ở `.place-item`

	.place-item {
	  //float: left;
	  width: 33.333333%;
	  //padding: 0 8px;
	}

153) Thêm vào `<div class="place-item">` class `col`

	<div class="col place-item">

154) Tạo `.col-third` 
	
	.col-third {
	  width: 33.33333%;
	}

155) Ẩn `width: 33.33333%` trong `.place-item`

	.place-item {
	  //float: left;
	  //width: 33.33333%;
	  //padding: 0 8px;
	}

156) Tại `<div class="col place-item">` thay `place-item` thành `col-third`.

157) Tại `#content .member-item` ẩn `width: 33.33333%;`
	
	#content .member-item {
	  float: left;
	  //width: 33.33333%;
	}

158) Thêm `col-third` vào `<div class="member-item">`

	<div class="member-item col-third">

159) Thêm `.text-center` 

	.text-center {
	  text-align: center !important;
	}

160) Thêm `.col-half` 

	.col-half {
	  width: 50%;
	}

161) Thêm `.col-full`

	.col-full {
	  width: 100%;
	} 

# 7. Contact form

162) Tạo 1 `row` chứa 2 `column` 

	<div class="row">
	  <div class="col col-half">
		    <p><i class="ti-location-pin"></i> Chicago, US</p>
		    <p><i class="ti-mobile"></i> Phone: +00 151515</p>
		    <p><i class="ti-email"></i> Email: mail@mail.com</p>
	  </div>
	
	  <div class="col col-half">
	    <form action="">
	      <div class="row">
	        <div class="col col-half"><input type="text" name="" placeholder="Name" id="" class="form-control"></div>
	        <div class="col col-half"><input type="email" name="" placeholder="Email" id="" class="form-control"></div>
	      </div>
	      <div class="row">
	        <div class="col col-full">
	          <input type="text" name="" placeholder="Message" id="" class="form-control">
	        </div>
	      </div>
	      <input type="submit" value="SEND">
	    </form>
	  </div>
	</div>

163) Thêm class `contact-content` vào `<div class="row">`

	<div class="row contact-content">
	
164) Thay đổi khoảng cách từ `contact-content` lên `section-sub-heading` của phần **Contact**

	.contact-content {
	  margin-top: 48px;
	}
	
165) Thêm vào  `<div class="col col-half">` đầu tiên class `contact-info`

	 <div class="col col-half contact-info">

166) Set font-size cho `.contact-info`
	
	.contact-info {
	  font-size: 18px;
	}

167) Thay đổi khoảng cách giữa icon và text cho `.contact-info`

Nên sử dụng `width` thay vì `margin`. Vì trong thực tế, 1 số icon có kích thước chiều rộng khác nhau nên sẽ dẫn đến text có thể bị lệch nếu sử dụng `margin`

	.contact-info i[class*="ti-"] {
	  width: 30px;
	  display: inline-block;
	}

CSS Selector nâng cao:

	.contact-info i[class*="ti-"] 
	
Chọn tất cả các thẻ `i` có tiền tố `ti-` là con của `.contact-info`

168) Thay đổi khoảng cách giữa 2 dòng chữ của `.contact-info`

	.contact-info {
	  line-height: 1.4;
	}
	
169) Thêm vào `<div class="col col-half">` thứ 2 class `contact-form`

	<div class="col col-half contact-form">
	
170) Set `font-size` cho `.contact-form"`
	
	.contact-form {
	  font-size: 15px;
	}

171) Customize lại `input` cho `.form-control`

	.contact-form .form-control {
	  padding: 10px;
	  border: 1px solid #ccc;
	  width: 100%;
	}

Có thể bỏ outline của thẻ input bằng thuộc tính `outline: none`

172) Thêm div `clear` vào sau `<div class="row">`

	<div class="clear"></div>

Hoặc chúng ta cũng có thể sử dụng Pseudo cho `.row` bằng cách
	
	.row::after {
	  content: "";
	  display: block;
	  clear: both;
	}
	
thay vì cứ phải thêm 1 div `clear` như trước.

173) Tạo 1 class `.mt-8` để `margin-top: 8px`
	
	.mt-8 {
	  margin-top: 8px !important;
	}

174) Thêm class `mt-8` vào input **Message** của `contact-form`

	<div class="col col-full mt-8">

175) Tạo 1 class `.mt-16` để `margin-top: 16px`
	
	.mt-16 {
	  margin-top: 16px !important;
	}

176) Thêm class `mt-16` vào `<input type="submit" value="SEND">`

	<input class="mt-16" type="submit" value="SEND">
	
177) Thêm class `form-submit-btn` vào `<input class="mt-16" type="submit" value="SEND">`

	<input class="mt-16" type="submit" value="SEND">

178) Customize lại `.form-submit-btn `

	.contact-form .form-submit-btn {
	  background-color: #000;
	  color: #fff;
	  border: 1px solid #000;
	  padding: 10px 16px;
	  float: right; 
	}

179) Thêm thuộc tính required vào thẻ input để có validate mặc định.

	<input type="text" name="" placeholder="Message" id="" class="form-control" required>

180) Đổi `place-buy-btn` thành `btn` ở cả HTML lẫn CSS

	// .place-buy-btn
	.btn {
	  color: #fff;
	  background-color: #000;
	  text-decoration: none;
	  padding: 11px 16px;
	  display: inline-block;
	  margin-top: 15px;
	}

181) Đổi `form-submit-btn` thành `btn` ở HTML, ở CSS xóa đi.

182) Ẩn border của `.btn` đi

	.btn {
	  border: none;
	}
	
183) Thêm style cusor cho `.btn` khi hover vào
	
	.btn:hover {
	  cursor: pointer;
	}
	
184) Thêm `.pull-right`

	.pull-right {
	  float: right !important;
	}

185) Thêm `pull-right` vào `<input class="mt-16 btn" type="submit" value="SEND">`

	<input class="mt-16 btn pull-right" type="submit" value="SEND">
	
Lưu ảnh map vào `assets/img`

# 8. Map

186) Thêm `map-section` và sau **Contact section**

	<div class="map-section">
	  <img src="./assets/img/map.jpeg" alt="Map">
	</div>

187) Set `width` cho `img`

	.map-section img {
	  width: 100%;
	}

# 9. Footer

188) Thêm `social-list` và `copyright`

    <div id="footer">
        <div class="socials-list">
          <a href=""><i class="ti-facebook"></i></a>
          <a href=""><i class="ti-instagram"></i></a>
          <a href=""><i class="ti-youtube"></i></a>
          <a href=""><i class="ti-pinterest"></i></a>
          <a href=""><i class="ti-twitter"></i></a>
          <a href=""><i class="ti-linkedin"></i></a>
        </div>
        <p class="copyright">Powered by <a href="w3.css">w3.css</a></p>
    </div>
   
189) Thêm `#footer` có `padding` và căn giữa

	#footer {
	  padding: 64px 16px;
	  text-align: center;
	}
	
190) Set `font-size` cho `.social-list`

	#footer .socials-list {
	  font-size: 24px;
	}

191) Đổi màu chữ và xóa gạch chân của thẻ `a`

	#footer .socials-list a {
	  color: rgba(0, 0, 0, 0.6);
	  text-decoration: none;
	}

192) Thêm hover cho `#footer .social-list a`

	#footer .socials-list a:hover {
	  opacity: 0.4;
	}

193) Thay đổi khoảng cách từ `.copyright` lên `.social-list` và màu chữ

	#footer .copyright {
	  margin-top: 15px;
	  color: rgba(0, 0, 0, 0.6);
	}

194) Đổi màu chữ cho `#footer .copyright a` 

	#footer .copyright a {
	  color: rgba(0, 0, 0, 0.6);
	}

195) Thêm hover cho `#footer .copyright a` 

# 9. Review

196) Thêm vào mỗi `div` 1 `id`, sau đó lên Navigation thêm vào href của từng mục `#id` đó. Khi click vào Navigation sẽ tự động trỏ vào phần chứa `id` đó.

197) Thêm vào thuộc tính `scroll-behavior` cho `html` để scroll mượt hơn.

	html {
	  scroll-behavior: smooth;
	}
