from facial_emotion_recognition 
import EmotionRecognition 
irport cv2. er EmotionRecognition (device-'cpu')
cam cv2.VideoCapture (1) #Intilizing Camera id
while True:
    sucess,frame cam.read()
    print (sucess) 
    frame er.recognise 
    emotion(frame, return type-'BGR') 
    cv2.imshow("Frame", frame)
    keycv2.waitKey(1) 
    print(key) 
    key=-27: 
        break
car.release() 
cv2.destroyAllWindows ()
