# จัดส่งแบบลงทะเบียนกับEMS

### จัดส่งแบบลงทะเบียน กับส่งแบบ EMS

ให้เราจำไว้ได้เลยจะตั้งค่าจัดส่งแบบไหนก็ตามเราต้องสร้างเขตจัดส่งสินค้าไว้ก่อนเสมอ \(Shipping zones\) ลองเข้าไปดูวิธีการเซ็ท [เขตจัดส่งสินค้า](https://padveewebschool.com/woocommerce-shipping-1/) ก่อนได้เลยครับ

#### สร้างเขตจัดส่งสินค้า

1.เมื่อเราเข้าสู่ระบบหลังบ้านให้เราไปที่ WooCommerce &gt; Settings &gt; จากนั้นให้เราคลิกที่ Shipping &gt;จากนั้นให้คลิก Add shipping zone

![&#xE01;&#xE32;&#xE23; &#xE15;&#xE31;&#xE49;&#xE07; &#xE04;&#xE48;&#xE32; shipping woocommerce](https://padveewebschool.com/wp-content/uploads/2018/06/Add-shipping-zone.png)

2. จากนั้นให้เราตั้งชื่อเขตการจัดส่งที่เราต้องการ ตั้งชื่อให้สื่อความหมายที่เข้าใจได้ง่าย เช่น กรุงเทพ และปริมณฑล, ต่างจังหวัด, ภาคกลาง, ภาคเหนือ หรืออะไรก็ได้ ตามที่เราต้องการ ในบทความนี้ผมขอตั้งเป็น “ทั่วประเทศ”

![Woocommerce &#xE04;&#xE48;&#xE32;&#xE08;&#xE31;&#xE14;&#xE2A;&#xE48;&#xE07;](https://padveewebschool.com/wp-content/uploads/2018/06/thailand-shipping-zone-02.jpg)

#### ตั้งค่าวิธีการจัดส่ง

1. เมื่อเข้ามาสู่หน้าเขตส่งสินค้าที่เราเลือก &gt; ให้เราคลิก Add shipping method

![woocommerce shipping](https://padveewebschool.com/wp-content/uploads/2018/06/add-shipping-method-02.jpg)

เลือก Flat rate &gt; แล้วคลิก Add shipping method

![&#xE2D;&#xE31;&#xE15;&#xE23;&#xE32;&#xE2A;&#xE48;&#xE07;&#xE04;&#xE07;&#xE17;&#xE35;&#xE48; Woocommerce](https://padveewebschool.com/wp-content/uploads/2018/06/choose-flatrate-02.jpg)

ที่ Shipping methods ตรง Flat rate &gt; ให้คลิก edit

![&#xE04;&#xE39;&#xE48;&#xE21;&#xE37;&#xE2D;&#xE43;&#xE0A;&#xE49;&#xE07;&#xE32;&#xE19; Woocommerce](https://padveewebschool.com/wp-content/uploads/2018/06/edit-shipping-methhods-02.jpg)

ตรง Method Title ให้เราเขียนข้อความเพื่อสื่อสารให้ลูกค้าได้เข้าใจว่าเรามีวิธีการจัดส่งอย่างไรบ้าง  และข้อความส่วนนี้ก็จะไปแสดงที่หน้า checkout ด้วย ในช่องราคาให้ใส่ราคาที่เราต้องการลงไป ในตัวอย่างนี้ผมคิดค่าจัดส่งแบบลงทะเบียน 50 บาทครับ

![&#xE15;&#xE31;&#xE49;&#xE07;&#xE04;&#xE48;&#xE32;&#xE08;&#xE31;&#xE14;&#xE2A;&#xE48;&#xE07;&#xE41;&#xE1A;&#xE1A;&#xE25;&#xE07;&#xE17;&#xE30;&#xE40;&#xE1A;&#xE35;&#xE22;&#xE19;](https://padveewebschool.com/wp-content/uploads/2018/06/woocommerce-04.jpg)

เมื่อกด save change เรียบร้อยแล้ว เราก็กลับไปทำเพิ่มรูปแบบการจัดส่งสินค้าอีกครั้งหนึ่ง  แต่คราวนี้ตรง Method Title ก็ให้ตั้งชื่อเป็น ส่งแบบ EMS และระบุราคาที่เราต้องการลงไปได้เลย

![](https://padveewebschool.com/wp-content/uploads/2018/06/add-ems-method.jpg)

![&#xE15;&#xE31;&#xE49;&#xE07;&#xE04;&#xE48;&#xE32; EMS Woocommerce](https://padveewebschool.com/wp-content/uploads/2018/06/Ems-shipping.jpg)

เมื่อทำทุกอย่างเรียบร้อย ผลลัพธ์ก็จะได้เป็น ดังนี้ โซนการจัดส่งสินค้า “ทั่วประเทศ” มีการคิดราคาจัดส่งสินค้า 2 รูปแบบ คือ จัดส่งแบบลงทะเบียน คิดค่าส่ง 50 บาท กับ การจัดส่งแบบ EMS คิดค่าส่ง 100 บาท

![&#xE2A;&#xE2D;&#xE19; woocommerce](https://padveewebschool.com/wp-content/uploads/2018/06/shipping-all-thailand-method.jpg)

ตัวอย่างใบสรุปค่าสินค้า+ค่าจัดส่ง

![Woocommerce order](https://padveewebschool.com/wp-content/uploads/2018/06/finish-shipping-order.jpg)

เป็นยังไงกันบ้างครับ การตั้งค่าจัดส่งสินค้า woocommerce ปรับแต่งไม่ยากเลย แล้วเดี๋ยวในบทความต่อไป ผมจะพูดถึง การตั้งค่า จัดส่งฟรีเมื่อซื้อตามยอดที่กำหนด คลิกเข้าไปอ่านต่อได้เลย

