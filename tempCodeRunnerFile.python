from transformers import pipeline
from googletrans import Translator

translator = Translator()
text_thai = "วันนี้ฉันต้องการร้องเรียนเกี่ยวกับประสบการณ์ในการใช้บริการโทรศัพท์ของบริษัทคุณ ฉันพบว่าการตอบโทรศัพท์จากพนักงานบริการของคุณมีความช้าลง และบางครั้งยังพบกับปัญหาในการเชื่อมต่อที่ไม่เสถียร ฉันหวังว่าคุณจะดำเนินการแก้ไขปัญหานี้และปรับปรุงคุณภาพการบริการให้ดียิ่งขึ้น ขอบคุณครับ/ค่ะ"
translated = translator.translate(text_thai, src='th', dest='en')
print(translated.text)

text_eng = translated.text

summarizer = pipeline("summarization", model="facebook/bart-large-cnn")

text_sum = summarizer(text_eng, max_length=130, min_length=30, do_sample=True)
text_sum

summarized_text = text_sum[0]['summary_text']
print(summarized_text)

translated2 = translator.translate(summarized_text, src='en', dest='th')
print(translated2.text)
