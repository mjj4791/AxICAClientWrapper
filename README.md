# AxICAClientWrapper
Wraper for AxICAClient to prevent crashes in ICAClient

Use this wrapper class for AxWFICALib.AxICAClient if you experience crashes as shown below. These crashes occur in the Citrix ICACLient control, for example when a form with the control on it is docked/undocked with the WeifenLuo DockPanelSuite (but theyre might be more cases where this happens)...
 
To use this wrapper, build your form as normally. Once happy, open the code for yout forms designer and replace in the 'InitializeComponent()':

    this.icaClient = new AxWFICALib.AxICAClient();
with

     this.icaClient = new AxICAClientWrapper.AxICAClientWrapper();

### NOTE
Make sure to compile your application, before trying to open the form!
The wrapper is in place only after a succesfull compile of the binary containing the wrapper...
 
# Exception:
==========
System.ArgumentException
HResult=0x80070057
Message=Parameter is not valid.
Source=System.Drawing
StackTrace:
  at System.Drawing.Font.ToLogFont(Object logFont, Graphics graphics)
  at System.Drawing.Font.ToLogFont(Object logFont)
  at System.Drawing.Font.ToHfont()
  at System.Windows.Forms.Control.FontHandleWrapper..ctor(Font font)
  at System.Windows.Forms.Control.get_FontHandle()
  at System.Windows.Forms.Control.get_FontHandle()
  at System.Windows.Forms.Control.get_FontHandle()
  at System.Windows.Forms.Control.get_FontHandle()
  at System.Windows.Forms.Control.get_FontHandle()
  at System.Windows.Forms.Control.SetWindowFont()
  at System.Windows.Forms.Control.OnFontChanged(EventArgs e)
  at System.Windows.Forms.AxHost.OnFontChanged(EventArgs e)
  at System.Windows.Forms.Control.OnParentFontChanged(EventArgs e)
  at System.Windows.Forms.Control.OnFontChanged(EventArgs e)
  at System.Windows.Forms.Control.OnParentFontChanged(EventArgs e)
  at System.Windows.Forms.Control.OnFontChanged(EventArgs e)
  at System.Windows.Forms.ContainerControl.OnFontChanged(EventArgs e)
  at System.Windows.Forms.Form.OnFontChanged(EventArgs e)
  at Connections.Forms.Conn.FrmConnectionCitrixWI.OnFontChanged(EventArgs e) in FrmSomeForm.cs:line 1046
  at System.Windows.Forms.Control.AssignParent(Control value)
  at System.Windows.Forms.Form.AssignParent(Control value)
  at System.Windows.Forms.Control.ControlCollection.Add(Control value)
  at System.Windows.Forms.Control.set_ParentInternal(Control value)
  at System.Windows.Forms.Form.set_ParentInternal(Control value)
  at System.Windows.Forms.Control.set_Parent(Control value)
  at WeifenLuo.WinFormsUI.Docking.DockContentHandler.SetParent(Control value)
  at WeifenLuo.WinFormsUI.Docking.DockContentHandler.SetPane(DockPane pane)
  at WeifenLuo.WinFormsUI.Docking.DockContentHandler.SetDockState(Boolean isHidden, DockState visibleState, DockPane oldPane)
  at WeifenLuo.WinFormsUI.Docking.DockContentHandler.set_Pane(DockPane value)
  at WeifenLuo.WinFormsUI.Docking.DockPane.InternalConstruct(IDockContent content, DockState dockState, Boolean flagBounds, Rectangle floatWindowBounds, DockPane prevPane, DockAlignment alignment, Double proportion, Boolean show)
  at WeifenLuo.WinFormsUI.ThemeVS2013.VS2013DockPane..ctor(IDockContent content, Rectangle floatWindowBounds, Boolean show)
  at WeifenLuo.WinFormsUI.ThemeVS2013.VS2013DockPaneFactory.CreateDockPane(IDockContent content, Rectangle floatWindowBounds, Boolean show)
  at WeifenLuo.WinFormsUI.Docking.DockContentHandler.FloatAt(Rectangle floatWindowBounds)
  at WeifenLuo.WinFormsUI.Docking.DockPanel.DockDragHandler.EndDrag(Boolean abort)
  at WeifenLuo.WinFormsUI.Docking.DockPanel.DockDragHandler.OnEndDrag(Boolean abort)
  at WeifenLuo.WinFormsUI.Docking.DockPanel.DragHandlerBase.EndDrag(Boolean abort)
  at WeifenLuo.WinFormsUI.Docking.DockPanel.DragHandlerBase.System.Windows.Forms.IMessageFilter.PreFilterMessage(Message& m)
  at System.Windows.Forms.Application.ThreadContext.ProcessFilters(MSG& msg, Boolean& modified)
  at System.Windows.Forms.Application.ThreadContext.PreTranslateMessage(MSG& msg)
  at System.Windows.Forms.Application.ThreadContext.System.Windows.Forms.UnsafeNativeMethods.IMsoComponent.FPreTranslateMessage(MSG& msg)
  at System.Windows.Forms.Application.ComponentManager.System.Windows.Forms.UnsafeNativeMethods.IMsoComponentManager.FPushMessageLoop(IntPtr dwComponentID, Int32 reason, Int32 pvLoopData)
  at System.Windows.Forms.Application.ThreadContext.RunMessageLoopInner(Int32 reason, ApplicationContext context)
  at System.Windows.Forms.Application.ThreadContext.RunMessageLoop(Int32 reason, ApplicationContext context)
  at System.Windows.Forms.Application.Run(Form mainForm)
  at Connections.Program.Main(String[] args) in Program.cs:line 115
 
