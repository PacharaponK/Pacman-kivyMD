Pacman คือ เกมแนวแอคชั่นคลาสสิกที่ผู้เล่นควบคุมตัวละคร Pacman เพื่อกินอาหารในสนามเกม และหลบหลีกผีที่มาไล่ Pacman ซึ่งผู้เล่นจะต้องใช้กลยุทธ์ในการเลี้ยวหรือหลบเพื่อรอด จบเกมเมื่อ Pacman ถูกจับโดยผีหรือกินลูกแก้วครบทุกในสนาม

การทำงานของโปรแกรม
    1. เมื่อผู้เล่นเข้ามาหน้าแรกจะต้องเลือกโหมดที่จะเล่นก่อน โดยรายละเอียดเเต่ละโหมดมีดังนี้
        1.1 Easy mode โหมดนี้จะมีผีเพียงตัวเดียวเพื่อให้เล่น Pacman ได้ง่ายขึ้น
        1.2 Normal mode โหมดนี้จะมีผี 2 ตัว เป็นโหมดที่ผู้เล่นทั่วไปเล่นผ่านได้
        1.3 Hard mode โหมดนี้จะมีผี 4 ตัว เพิ่มความท้าทายให้กับผู้เล่นที่ชอบอะไรยากๆ
    2. เมื่อเลือกโหมดเสร็จ ผู้เล่นจะต้องเดินกินอาหารตามทาง โดยไม่ให้ผีจับได้
    3. ในเเผนที่จะมี powerball เป็นลูกบอลกลมๆเมื่อเรากินเข้าไป เราจะสามารถกินผีได้ 1 ตัว
    4. เมื่อกินอาหารครบหมดเเล้ว ผู้เล่นก็จะชนะ
    5. ผู้เล่นจะเเพ้ก็ต่อเมื่อผีไล่ตามเราทันเเละชนกับเรา t - t

ฟังก์ชั่นหลักๆของโปรเเกรม
    1. ไฟล์ main.py ประกอบไปด้วย
        1.1 show_food() ทำหน้าที่เเสดงอาหาร
        1.2 update() ทำหน้าที่อัพเดทเกมให้ pacman เดิน, ตรวจสอบว่าเราผีชนเรายัง และลบผีเมื่อชนและมี powerball
        1.3 update_ghost{:id}() ทำหน้าที่ควบคุมการเคลื่อนที่ของผี
        1.4 do_strategy{:id}() ทำหน้าที่ตัดสินใจว่าผีควรจะเดินไปทางไหน เพื่อให้ชนผู้เล่น
        1.5 build() ทำหน้าที่รวมทุกอยากเพื่อสร้างเป็นเกม pacman 
    2. ไฟล์ player.py ฟังก์ชั่นการทำงานหลักๆคือ สร้างขอบเขตการเดินตาม Widget Wall ที่เราวางไว้ เเละสร้าง portal 
        2.1 move() ทำหน้าที่ควบคุมการเดินขึ้นลงซ้ายขวาของ pacman และให้เคลื่อนที่ตามขอบเขต(bound) ที่เราวางไว้เท่านั้น
    3. ไฟล์ food.py ฟังก์ชั่นการทำงานหลักๆคือ นำขอบเขต(bound) มาใส่เพื่อเเสดงอาหารและลบเมื่อถูกกิน
    4. ไฟล์ gostBrain.py เราจะนำอัลกอรึทิม dijkstra มาใช้เพื่อหาระยะทางที่สั้นที่สุดที่ผีจะไปหาผู้เล่นได้
    5. ไฟล์ ghost.py มีฟังก์ชั่น move() ที่ลอกไฟล์ player.py มา เเต่ที่เพิ่มมาคือการนำ gostBrain.py                      มาใช้เพื่อเป็นสมองของผีให้คอยไล่ตามผู้เล่น
    6. ไฟล์ powerball มีฟังก์ชั่นที่คอยตรวจสอบว่าผู้เล่นกิน powerball แล้วหรือยัง