# maui-shell-titleview-android-crash

This project demonstrates the issue of a maui app crashing on Android with a `Shell.TitleView` when navigating back to it

https://github.com/dotnet/maui/issues/4506


```
02-04 08:55:10.322  8890  8890 I MonoDroid: UNHANDLED EXCEPTION:
02-04 08:55:10.348  8890  8890 I MonoDroid: Java.Lang.IllegalStateException: The specified child already has a parent. You must call removeView() on the child's parent first.
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Java.Interop.JniEnvironment.InstanceMethods.CallNonvirtualVoidMethod(JniObjectReference instance, JniObjectReference type, JniMethodInfo method, JniArgumentValue* args)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Java.Interop.JniPeerMembers.JniInstanceMethods.InvokeVirtualVoidMethod(String encodedMember, IJavaPeerable self, JniArgumentValue* parameters)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Android.Views.ViewGroup.AddView(View child)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Handlers.LayoutHandler.SetVirtualView(IView view)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Handlers.ViewHandler`2[[Microsoft.Maui.ILayout, Microsoft.Maui, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null],[Microsoft.Maui.Platform.LayoutViewGroup, Microsoft.Maui, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]].SetVirtualView(IElement view)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Element.SetHandler(IElementHandler newHandler)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Element.set_Handler(IElementHandler value)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.VisualElement.Microsoft.Maui.IElement.set_Handler(IElementHandler value)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Platform.ElementExtensions.ToHandler(IElement view, IMauiContext context)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Platform.ElementExtensions.ToNative(IElement view, IMauiContext context)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellContentView.OnViewSet(View view)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellContentView.set_View(View value)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellContentView..ctor(Context context, View view, IMauiContext mauiContext)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellContainerView.OnViewSet(View view)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellContainerView.set_View(View value)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellContainerView..ctor(Context context, View view, IMauiContext mauiContext)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellToolbarTracker.UpdateTitleView(Context context, Toolbar toolbar, View titleView)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellToolbarTracker.UpdateTitleView()
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellToolbarTracker.OnPageChanged(Page oldPage, Page newPage)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellToolbarTracker.set_Page(Page value)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at Microsoft.Maui.Controls.Platform.ShellSectionView.OnCreateView(LayoutInflater inflater, ViewGroup container, Bundle savedInstanceState)
02-04 08:55:10.348  8890  8890 I MonoDroid:    at AndroidX.Fragment.App.Fragment.n_OnCreateView_Landroid_view_LayoutInflater_Landroid_view_ViewGroup_Landroid_os_Bundle_(IntPtr jnienv, IntPtr native__this, IntPtr native_inflater, IntPtr native_container, IntPtr native_savedInstanceState)
02-04 08:55:10.349  8890  8890 I MonoDroid:   --- End of managed Java.Lang.IllegalStateException stack trace ---
02-04 08:55:10.349  8890  8890 I MonoDroid: java.lang.IllegalStateException: The specified child already has a parent. You must call removeView() on the child's parent first.
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at android.view.ViewGroup.addViewInner(ViewGroup.java:5235)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at android.view.ViewGroup.addView(ViewGroup.java:5064)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at android.view.ViewGroup.addView(ViewGroup.java:5004)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at android.view.ViewGroup.addView(ViewGroup.java:4976)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at crc64338477404e88479c.ShellSectionView.n_onCreateView(Native Method)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at crc64338477404e88479c.ShellSectionView.onCreateView(ShellSectionView.java:42)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at androidx.fragment.app.Fragment.performCreateView(Fragment.java:2963)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentStateManager.createView(FragmentStateManager.java:518)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentStateManager.moveToExpectedState(FragmentStateManager.java:282)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentManager.executeOpsTogether(FragmentManager.java:2189)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentManager.removeRedundantOperationsAndExecute(FragmentManager.java:2100)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentManager.execPendingActions(FragmentManager.java:2002)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentManager$5.run(FragmentManager.java:524)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at android.os.Handler.handleCallback(Handler.java:938)
02-04 08:55:10.349  8890  8890 I MonoDroid: 	at android.os.Handler.dispatchMessage(Handler.java:99)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.os.Looper.loop(Looper.java:223)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.app.ActivityThread.main(ActivityThread.java:7656)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at java.lang.reflect.Method.invoke(Native Method)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at com.android.internal.os.RuntimeInit$MethodAndArgsCaller.run(RuntimeInit.java:592)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:947)
02-04 08:55:10.350  8890  8890 I MonoDroid: 
02-04 08:55:10.350  8890  8890 I MonoDroid:   --- End of managed Java.Lang.IllegalStateException stack trace ---
02-04 08:55:10.350  8890  8890 I MonoDroid: java.lang.IllegalStateException: The specified child already has a parent. You must call removeView() on the child's parent first.
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.view.ViewGroup.addViewInner(ViewGroup.java:5235)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.view.ViewGroup.addView(ViewGroup.java:5064)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.view.ViewGroup.addView(ViewGroup.java:5004)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.view.ViewGroup.addView(ViewGroup.java:4976)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at crc64338477404e88479c.ShellSectionView.n_onCreateView(Native Method)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at crc64338477404e88479c.ShellSectionView.onCreateView(ShellSectionView.java:42)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at androidx.fragment.app.Fragment.performCreateView(Fragment.java:2963)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentStateManager.createView(FragmentStateManager.java:518)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentStateManager.moveToExpectedState(FragmentStateManager.java:282)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentManager.executeOpsTogether(FragmentManager.java:2189)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentManager.removeRedundantOperationsAndExecute(FragmentManager.java:2100)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentManager.execPendingActions(FragmentManager.java:2002)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at androidx.fragment.app.FragmentManager$5.run(FragmentManager.java:524)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.os.Handler.handleCallback(Handler.java:938)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.os.Handler.dispatchMessage(Handler.java:99)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.os.Looper.loop(Looper.java:223)
02-04 08:55:10.350  8890  8890 I MonoDroid: 	at android.app.ActivityThread.main(ActivityThread.java:7656)
02-04 08:55:10.351  8890  8890 I MonoDroid: 	at java.lang.reflect.Method.invoke(Native Method)
02-04 08:55:10.351  8890  8890 I MonoDroid: 	at com.android.internal.os.RuntimeInit$MethodAndArgsCaller.run(RuntimeInit.java:592)
02-04 08:55:10.351  8890  8890 I MonoDroid: 	at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:947)
02-04 08:55:10.351  8890  8890 I MonoDroid: 
02-04 08:55:10.357   529  8933 I DropBoxManagerService: add tag=data_app_crash isTagEnabled=true flags=0x2
02-04 08:55:10.357   529  2149 W ActivityTaskManager:   Force finishing activity com.companyname.titleviewtestapp/crc6478eb02fbad93c8d6.MainActivity

```
