# So sánh vmalloc và kmalloc

-  vmalloc thường chậm hơn kmalloc, bởi vì nó có thể phải ánh xạ lại không gian bộ đệm thành một phạm vi hầu như liền kề. kmalloc không bao giờ ánh xạ lại, mặc dù nếu không được gọi bằng GFP_ATOMIC kmalloc có thể chặn.
-  kmalloc bị giới hạn về kích thước bộ đệm mà nó có thể cung cấp: (128 KBytes*). Nếu bạn cần một bộ đệm thực sự lớn, bạn phải sử dụng vmalloc hoặc một số cơ chế khác như dự trữ bộ nhớ cao khi khởi động.
