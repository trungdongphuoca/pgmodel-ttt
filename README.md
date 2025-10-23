Dự đoán Ý định mua hàng của Khách hàng bằng Mô hình Đồ thị Xác suất (PGM)

Đây là hướng dẫn để chạy file Jupyter Notebook Prediction of online shoppers’ purchasing intention using Probabilistic Graphical Models.ipynb sử dụng Google Colab.

Các bước thực hiện

Tải file Notebook:

Tải file Prediction of online shoppers’ purchasing intention using Probabilistic Graphical Models.ipynb về máy tính của bạn.

Upload Notebook lên Google Colab:

Truy cập Google Colab.

Chọn "Tải tệp lên" (Upload) và chọn file notebook bạn vừa tải về.

Upload Dữ liệu:

Trong môi trường Google Colab, bạn cần tải file dữ liệu online_shoppers_intention.csv lên.

Tìm và tải bộ dữ liệu "Online Shoppers Purchasing Intention Dataset" từ UCI Machine Learning Repository hoặc nguồn bạn có. File cần có tên là online_shoppers_intention.csv.

Trong Colab, ở thanh bên trái, nhấp vào biểu tượng thư mục (Files).

Nhấp vào biểu tượng "Tải lên tệp" (Upload to session storage) và chọn file online_shoppers_intention.csv.

Lưu ý: File này sẽ bị xóa khi phiên Colab kết thúc. Bạn cần tải lên lại mỗi khi bắt đầu phiên mới.

Chuyển môi trường sang ngôn ngữ R:

Trên thanh menu của Colab, chọn "Thời gian chạy" (Runtime).

Chọn "Thay đổi loại thời gian chạy" (Change runtime type).

Trong menu thả xuống "Loại thời gian chạy", chọn "R".

Nhấp "Lưu" (Save).

Cài đặt các thư viện R cần thiết:

Chạy các ô code đầu tiên trong notebook để cài đặt các gói thư viện R. Các lệnh cài đặt bao gồm:

# Cài đặt các thư viện cần thiết
install.packages("dplyr")
install.packages("lubridate")
install.packages("bnlearn")
# Cài đặt gói từ Bioconductor
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install(c("graph", "Rgraphviz"), update=FALSE)
# Cài đặt các gói khác
if(!require(corrplot)) install.packages("corrplot")
if(!require(DescTools)) install.packages("DescTools", dependencies=TRUE)
if(!require(caTools)) install.packages("caTools")
install.packages("ggplot2")
install.packages("tidyr")
install.packages("readr") 


Lưu ý: Quá trình cài đặt có thể mất vài phút.

Chạy lần lượt các đoạn code:

Sau khi cài đặt xong thư viện và môi trường R đã sẵn sàng, bạn có thể chạy lần lượt từng ô code trong notebook từ trên xuống dưới.

Nhấn Shift + Enter hoặc nút ▶️ bên cạnh mỗi ô code để thực thi.

Đảm bảo rằng ô code trước đó đã chạy xong trước khi chạy ô tiếp theo.