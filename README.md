# setTextPerformance
Explanation about bad setText performance

Don't use TextView.setText() with layout_width="wrap_content" in performance critical areas like onBindView or onScroll.

This operation is very slow and blocks UI and makes the scrolling jerky.

This happens because of width of the view changes on new text (wrap effect) and requestLayout() needs recalculate, relayout and redraw all the surroundings.

What you can do? Change to layout_width="match_parent" if appicable or layout_width="0dp" and setup ConstrintLayout constraints. Or use fixed width.
