# RecyclerView season 2

Adapter : 어댑터는 앱별 데이터 세트에서 RecyclerView 내에 표시되는 뷰에 바인딩을 제공한다.

그러니까, 어댑터는 리사이클러뷰를 갱신하고, 데이터들을 관리한다.
이 어댑터들이 리사이클러뷰의 뷰들을 관리하게 쉽게 만들게 도와주는 것들이 바로 ViewHolder.

ViewHolder : recyclerview들의 아이템 뷰들은, 뷰 홀더를 사용하여 뷰 홀더가 아이템 뷰들에 내용을 추가하기 쉽게 해준다.

RecyclerView에 아이템이 추가될 때마다,
Adapter는 ViewHolder를 생성하고(onCreateViewHolder()),

그 해당되는 아이템에 viewholder에게 정보를 전달하라고 한다.
(onBindViewHolder())

해당되는 아이템의 위치를 구하기 위해 getItemCount() 메서드를 구현한다.

