input_real:           32,3,224,224   -->  Variable()

input_cropped:   32,3,224,224   -->  Variable()

real_label = 1

fake_label = 1

real_center : 	  32,3,112,112   -->  Variable()

optimizerD = Adam(netD)	-->  _netlocalD	-->  ==Discriminator==

- input:  64, 64 	-->   output 1, 	-->  True or False
- output 1与图像尺寸有关，当且仅当128时成立，若采用其他尺寸，需要修改最后一层卷积

optimizerG = Adam(netG)	-->  _netG	-->  ==AlexNet+Decoder==

- input: 128, 128 	-->   output 64, 64



real_cpu     			32,3,224,224

real_center_cpu    32,3,112,112

ｅｒｒＤ＿ｒｅａｌ＝ｃｒｉｔｅｒｉｏｎ（ｏｕｔｐｕｔ，ｌａｂｅｌ）

ｆａｋｅ　



---



1. 生成marker
2. 分train val test（==pass optional==）
3. resize后生成cropped mask 	-->    cv2.imread(mask_i.jpg) and resize() 	--> mask over img_src to get ==input_cropped==
4. create txt, including (img_file_name, center x, center y)
5. using txt to get ==real_center_cpu==
6. train.py 
   1. read real_cpu, read real_center_cpu, input_cropped  
   2. predict fake, discriminator results
   3. calculate l2 loss(), nn.BCEloss()



