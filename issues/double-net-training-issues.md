
  # Double Net Training Issues
  
  Started training my network with SqueezeNet computing the metadata from two input images, and then feeding this data to a pretrained model of Z2Color in evaluate mode. The goal was to have SqueezeNet able to infer metadata completely. Unfortuantely I ran into a training error where each epoch has extremely similar validation error and the squeeze net is not learning anything.
  
  ```
  schowdhuri@bdd3:~/working-directory/training_grounds/metadata-inference/save$ ls -lh -v1 | head -n 6
  total 2.5G
  -rw-rw-r-- 1 schowdhuri schowdhuri 2.8M May  8 04:02 epoch_save_0.0.00471940683692
  -rw-rw-r-- 1 schowdhuri schowdhuri 2.8M May  8 18:32 epoch_save_1.0.00471963190057
  -rw-rw-r-- 1 schowdhuri schowdhuri 2.8M May  9 08:57 epoch_save_2.0.00471670082341
  -rw-rw-r-- 1 schowdhuri schowdhuri 2.8M May  9 23:18 epoch_save_3.0.0047228806786
  -rw-rw-r-- 1 schowdhuri schowdhuri 2.8M May 10 13:38 epoch_save_4.0.00472525949612
  ```
  
  It's probably some error in the modified training code. So I'm going to sit down and compare my new training code to the old one line by line to see if I messed anything up.

  **ISSUE SOLVED IN DAILY LOG 5/12/17 (Creation of new metadata variable is breaking the backpropagation chain and isn't optimizing anything)**
