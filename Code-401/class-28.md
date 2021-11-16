# RecyclerView

Imagine you have large set of data and you want to display it in a list, but you don’t want to create a new activity for each item in the list (which is bad for memory and performance) or you want to display the data in a different way (e.g. in a card) so we use RecyclerView.

RecyclerView is a layout manager that can be used to present data in a scrollable list. It is a more advanced version of ListView and GridView.

How to implement RecyclerView?

- First of all, decide what the list or grid is going to look like. Ordinarily you'll be able to use one of the RecyclerView library's standard layout managers.

- Design how each element in the list is going to look and behave. Based on this design, extend the ViewHolder class. Your version of ViewHolder provides all the functionality for your list items. Your view holder is a wrapper around a View, and that view is managed by RecyclerView.

- Define the Adapter that associates your data with the ViewHolder views.

Plan your layout:

The items in your RecyclerView are arranged by a LayoutManager class. The RecyclerView library provides three layout managers, which handle the most common layout situations:

    LinearLayoutManager:
        - A basic layout manager that arranges items in a linear list.
        - The default layout manager for RecyclerView.
    GridLayoutManager:
        - A layout manager that arranges items in a grid.
    StaggeredGridLayoutManager:
        - A layout manager that arranges items in a staggered grid.

Implementing your adapter and view holder:

Now we have created our RecyclerView, we need to implement the Adapter and ViewHolder classes by override the following methods:

    onCreateViewHolder:
        - Called by the RecyclerView to display the data at the specified position. This method should instantiate the ViewHolder and return it.
    onBindViewHolder:
        - Called by the RecyclerView to display the data at the specified position. This method should update the ViewHolder to display the correct data.
    getItemCount:
        - Returns the total number of items in the data set hold by the adapter.

```java



public class CustomAdapter extends RecyclerView.Adapter<CustomAdapter.ViewHolder> {

    private String[] localDataSet;

    /**
     * Provide a reference to the type of views that you are using
     * (custom ViewHolder).
     */
    public static class ViewHolder extends RecyclerView.ViewHolder {
        private final TextView textView;

        public ViewHolder(View view) {
            super(view);
            // Define click listener for the ViewHolder's View

            textView = (TextView) view.findViewById(R.id.textView);
        }

        public TextView getTextView() {
            return textView;
        }
    }

    /**
     * Initialize the dataset of the Adapter.
     *
     * @param dataSet String[] containing the data to populate views to be used
     * by RecyclerView.
     */
    public CustomAdapter(String[] dataSet) {
        localDataSet = dataSet;
    }

    // Create new views (invoked by the layout manager)
    @Override
    public ViewHolder onCreateViewHolder(ViewGroup viewGroup, int viewType) {
        // Create a new view, which defines the UI of the list item
        View view = LayoutInflater.from(viewGroup.getContext())
                .inflate(R.layout.text_row_item, viewGroup, false);

        return new ViewHolder(view);
    }

    // Replace the contents of a view (invoked by the layout manager)
    @Override
    public void onBindViewHolder(ViewHolder viewHolder, final int position) {

        // Get element from your dataset at this position and replace the
        // contents of the view with that element
        viewHolder.getTextView().setText(localDataSet[position]);
    }

    // Return the size of your dataset (invoked by the layout manager)
    @Override
    public int getItemCount() {
        return localDataSet.length;
    }
}

```

The xml File "text_row_item.xml"

```xml

<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="@dimen/list_item_height"
    android:layout_marginLeft="@dimen/margin_medium"
    android:layout_marginRight="@dimen/margin_medium"
    android:gravity="center_vertical">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/element_text"/>
</FrameLayout>

```
