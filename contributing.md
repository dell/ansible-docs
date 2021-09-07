# Contribution

## Adding the new topic 
The table of contents is built dynamically using the directory structure of the documentation source. Each subdirectory has a file  _index.md`, which represents the "home" page for a given subdirectory's content. The `_index.md` does not need a template. It can contain overview content about the topics in the subdirectory.

### Adding title to your topic
In your topic, put a `title` field in the [front matter](https://gohugo.io/content-management/front-matter/). The front matter is the YAML block that is between the triple-dashed lines at the top of the page. Here's an example:
    ---
    title: Installation
    ---

### Adding media file to a topic
To add any media file like images, videos and PDFs add it under their respective directory under static directory. For example, Put image files in the `static/images` directory.

## Documentation formatting standards

### Use upper camel case for API objects

When you refer specifically to interacting with an API object, use [UpperCamelCase](https://en.wikipedia.org/wiki/Camel_case), also known as Pascal Case. When you are generally discussing an API object, use [sentence-style capitalization](https://docs.microsoft.com/en-us/style-guide/text-formatting/using-type/use-sentence-style-capitalization).

Don't split the API object name into separate words. For example, use PodTemplateList, not Pod Template List.

"Do and Don't - API objects"
Do | Don't
:--| :-----
The pod has two containers. | The Pod has two containers.
The HorizontalPodAutoscaler is responsible for ... | The HorizontalPodAutoscaler object is responsible for ...
A PodList is a list of pods. | A Pod List is a list of pods.
The two ContainerPorts ... | The two ContainerPort objects ...

### Use angle brackets for placeholders

Use angle brackets for placeholders. Tell the reader what a placeholder
represents.

1. Display information about a pod:

        kubectl describe pod <pod-name> -n <namespace>

### Use bold for user interface elements

"Do and Don't - Bold interface elements"
Do | Don't
:--| :-----
Click **Fork**. | Click "Fork".
Select **Other**. | Select "Other".

### Use code style for filenames, directories, and paths

"Do and Don't - Use code style for filenames, directories, and paths"
Do | Don't
:--| :-----
Open the `envars.yaml` file. | Open the envars.yaml file.
Go to the `/docs/tutorials` directory. | Go to the /docs/tutorials directory.
Open the `/_data/concepts.yaml` file. | Open the /\_data/concepts.yaml file.

## Inline code formatting

### Use code style for inline code, commands, and API objects

For inline code in an HTML document, use the `<code>` tag. In a Markdown
document, use the backtick (`` ` ``).

"Do and Don't - Use code style for inline code and commands"
Do | Don't
:--| :-----
The `kubectl run` command creates a `Pod`. | The "kubectl run" command creates a pod.
The kubelet on each node acquires a `Lease`… | The kubelet on each node acquires a lease…
A `PersistentVolume` represents durable storage… | A Persistent Volume represents durable storage…
For declarative management, use `kubectl apply`. | For declarative management, use "kubectl apply".
Enclose code samples with triple backticks. (\`\`\`)| Enclose code samples with any other syntax.
Use single backticks to enclose inline code. For example, `var example = true`. | Use two asterisks (`**`) or an underscore (`_`) to enclose inline code. For example, **var example = true**.
Use triple backticks before and after a multi-line block of code for fenced code blocks. | Use multi-line blocks of code to create diagrams, flowcharts, or other illustrations.
Use meaningful variable names that have a context. | Use variable names such as 'foo','bar', and 'baz' that are not meaningful and lack context.
Remove trailing spaces in the code. | Add trailing spaces in the code, where these are important, because the screen reader will read out the spaces as well.

### Use code style for object field names and namespaces

"Do and Don't - Use code style for object field names"
Do | Don't
:--| :-----
Set the value of the `replicas` field in the configuration file. | Set the value of the "replicas" field in the configuration file.
The value of the `exec` field is an ExecAction object. | The value of the "exec" field is an ExecAction object.
Run the process as a Daemonset in the `kube-system` namespace. | Run the process as a Daemonset in the kube-system namespace.


### Use code style for Kubernetes command tool and component names

"Do and Don't - Use code style for Kubernetes command tool and component names"
Do | Don't
:--| :-----
The kubelet preserves node stability. | The `kubelet` preserves node stability.
The `kubectl` handles locating and authenticating to the API server. | The kubectl handles locating and authenticating to the apiserver.
Run the process with the certificate, `kube-apiserver --client-ca-file=FILENAME`. | Run the process with the certificate, kube-apiserver --client-ca-file=FILENAME. |

### Use normal style for string and integer field values

For field values of type string or integer, use normal style without quotation marks.

"Do and Don't - Use normal style for string and integer field values"
Do | Don't
:--| :-----
Set the value of `imagePullPolicy` to Always. | Set the value of `imagePullPolicy` to "Always".
Set the value of `image` to nginx:1.16. | Set the value of `image` to `nginx:1.16`.
Set the value of the `replicas` field to 2. | Set the value of the `replicas` field to `2`.
 
## Code snippet formatting

### Don't include the command prompt

"Do and Don't - Don't include the command prompt" 
Do | Don't
:--| :-----
kubectl get pods | $ kubectl get pods

### Separate commands from output

Verify that the pod is running on your chosen node:

    kubectl get pods --output=wide

The output is similar to this:

    NAME     READY     STATUS    RESTARTS   AGE    IP           NODE
    nginx    1/1       Running   0          13s    10.200.0.4   worker0


Source: https://kubernetes.io/docs/contribute/style/style-guide/