> This documentation page needs to be better.

# Welcome to the mission!
Whether you're here to harden the Host Engine or expand the Guest Plugin ecosystem, here is your path to your first contribution:

!!! info "Plugin only development"
    You do not need to setup development enviroment if you are intrested in only building plugins.
    Please follow [Plugin Developer Guide](./plugin/creating-plugin.md) for more information.

# Set up development enviroment
> Github repository:
> https://github.com/razorblade23/hydrust.git

1. Setup & Environment
- [x] Prerequisites: **Docker** (or **Podman**) and **VS Code** with `DevContainers` extension installed
- [x] Clone the repository: Fork and clone the **Hydrust** repository.
- [x] Build *devcontainer*: A popup should appear in the bottom-right corner asking to "*Reopen in Container*". Click it!
- [x] Wait for the magic: *VS Code* will now pull a specialized Rust image and install all the **GStreamer** headers for you automatically

2. Choose Your Path
- [ ] The "Host" Track: Head over to <#1469126920036683786>  if you want to work on GStreamer, muxing logic, or the Rust core.
- [ ] The "Guest" Track: Head over to <#1469127023145390110>  if you want to build or maintain site-specific scrapers.
- [ ] The "Scribe" Track: Browse <#1469150932745977949>  for any threads tagged with 📝 WIP that need more detail.

3. Your First Contribution (The "Low-Hanging Fruit")
-  [ ] Audit a Plugin: Pick a site plugin in the library and verify if it still works with the latest site layout.
- [ ] Documentation: Found a step in the setup that was confusing? Open a thread in <#1469150932745977949>  with the fix.
- [ ] Test Drive: Run the engine against a high-concurrency manifest and report any panics in <#1469130877077291122> .

4. Join the Conversation
- [ ] Introduce yourself in <#1469101324632068329> .
- [ ] Check the <#1469125575120654336>  to see what architectural changes are being debated.