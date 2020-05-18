안드로이드 공부를 하면서 앱을 만들때 목록을 표시할 일이 많은데 그럴때 가장많이 사용한다고 생각한 RecyclerView에 대해 정리해 보겠다.
# RecyclerView란?
ListView가 더 진보된 버전,
앱에서 대량의 데이터 세트 또는 자주 변경되는 데이터에 기반한 요소의 스크롤 목록을 표시해야 한다면 recyclerview를 사용하라고 Android Developer에선 얘기한다.

# RecyclerView 사용법

레이아웃에 RecyclerView 객체를 추가하면, recyclerview의 배치를 layoutManager의 종류에 따라 바꿀수 있다.
예를 들어, linearlayoutManager로 한다면 linearlayout처럼 가로/세로의 형태로 배치가 된다.

그 후 표시될 데이터의 어댑터를 recyclerview에 연결한다.

어댑터에서 viewholder의 정의에 따라 목록의 view가 정의되고,
항목의 뷰를 만들고 원래의 항목이 더 이상 표시되지 않을 때 일부 뷰의 콘텐츠를 새 데이터 항목으로 교체한다.
* 어댑터 예시
     class MyAdapter(private val myDataset: Array<String>) :
            RecyclerView.Adapter<MyAdapter.MyViewHolder>() {

        //각 데이터 항목의 view에 대한 reference를 제공함.
        class MyViewHolder(val textView: TextView) : RecyclerView.ViewHolder(textView)

        // 새로운 뷰를 만듬 (layout manager가 적용함.)
        override fun onCreateViewHolder(parent: ViewGroup,
                                        viewType: Int): MyAdapter.MyViewHolder {
            
            val textView = LayoutInflater.from(parent.context)
                    .inflate(R.layout.my_text_view, parent, false) as TextView
         
            ...
            return MyViewHolder(textView)
        }

        // view의 내용을 교체한다.(ayout manager가 적용함.)
        override fun onBindViewHolder(holder: MyViewHolder, position: Int) {
            // - get element from your dataset at this position
            // - replace the contents of the view with that element
            holder.textView.text = myDataset[position]
        }

        // 데이터 셋의 크기를 반환한다. (layout manager가 적용함.)
        override fun getItemCount() = myDataset.size
    }
    
