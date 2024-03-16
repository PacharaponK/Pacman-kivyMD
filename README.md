# Pacman Game

## คำอธิบาย
Pacman เป็นเกมแนวแอคชั่นคลาสสิกที่ผู้เล่นควบคุมตัวละคร Pacman เพื่อกินอาหารในสนามเกม และหลบหลีกผีที่มาไล่ Pacman ซึ่งผู้เล่นจะต้องใช้กลยุทธ์ในการเลี้ยวหรือหลบเพื่อรอด การเล่นจบเมื่อ Pacman ถูกจับโดยผีหรือกินลูกแก้วครบทุกในสนาม

## วิธีการใช้งาน
1. เมื่อเริ่มเกมผู้เล่นจะต้องเลือกโหมดที่ต้องการเล่นตามระดับความยากดังนี้:
    - **Easy mode:** มีผีเพียงตัวเดียวเพื่อให้เล่น Pacman ได้ง่ายขึ้น
    - **Normal mode:** มีผี 2 ตัว เป็นโหมดที่ผู้เล่นทั่วไปเล่นผ่านได้
    - **Hard mode:** มีผี 4 ตัว เพิ่มความท้าทายให้กับผู้เล่นที่ชอบอะไรยากๆ

2. เลือกโหมดเสร็จสิ้นแล้วผู้เล่นจะควบคุม Pacman เดินเพื่อกินอาหาร โดยหลีกเลี่ยงการถูกผีจับ

3. ในเส้นทางอาจมี powerball ซึ่งเป็นลูกบอลกลมๆ หาก Pacman กินเข้าไปจะทำให้ Pacman สามารถกินผีได้ 1 ตัว

4. เมื่อ Pacman กินอาหารครบทุกในสนาม ผู้เล่นจะชนะเกม

5. ผู้เล่นจะแพ้เกมเมื่อ Pacman ถูกผีจับได้หรือถูกชนโดยผี

## ฟังก์ชันหลัก
1. **main.py:** ไฟล์หลักของเกม Pacman ประกอบด้วยฟังก์ชันต่าง ๆ ที่ให้การทำงานดังนี้:
    - `show_food():` แสดงตำแหน่งของอาหารในเกม
    - `update():` อัพเดทการเคลื่อนที่ของ Pacman และตรวจสอบการชนของ Pacman กับผี
    - `update_ghost{id}():` อัพเดทการเคลื่อนที่ของผี
    - `do_strategy{id}():` ตัดสินใจเส้นทางการเดินของผีเพื่อหาระยะทางที่สั้นที่สุดที่ Pacman จะถูกจับ
    - `build():` สร้างและรวมฟังก์ชันทั้งหมดเพื่อสร้างเกม Pacman

2. **player.py:** ไฟล์ที่ควบคุมการเคลื่อนที่ของ Pacman โดยกำหนดขอบเขตการเดินตามขอบเขต (bound) และสร้าง portal สำหรับ Pacman

3. **food.py:** ไฟล์ที่แสดงตำแหน่งของอาหารในเกมและลบอาหารเมื่อ Pacman กิน

4. **ghostBrain.py:** ไฟล์ที่ใช้วิธีอัลกอริทึม Dijkstra เพื่อหาเส้นทางที่สั้นที่สุดที่ผีจะไปหา Pacman

5. **ghost.py:** ไฟล์ที่ควบคุมการเคลื่อนที่ของผีโดยใช้เทคนิคจากไฟล์ ghostBrain.py เพื่อเป็นสมองของผีในการไล่ Pacman

6. **powerball.py:** ไฟล์ที่ตรวจสอบว่า Pacman ได้กิน powerball หรือยัง

