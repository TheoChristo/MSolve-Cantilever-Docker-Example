
# MSolve Cantilever Docker Example

A .NET Console Application that uses MSolve to solve a simple Cantilever problem. It can be shiped and launched inside a Docker Container for cross-platform compatibility.

## Use

* Publish the app to create the corresponding binary

    ```cli
    dotnet publish -c Release
    ```

    This will generate a *CantileverExampleDocker.Docker.dll* inside `bin/Release/net5.0/publish/`

*<b>Note:</b> From this point onwards, you -obviously- need Docker installed and running on your machine.*

* Create Docker Image

    ```cli
    docker build -t msolve-cantilever-image -f Dockerfile .
    ```

    You can verify that the docker image was created by running

    ```cli
    docker images
    ```

* Create and Run Docker Container
  
  * If you just want to launch a Cantilever Example Docker container, you can run

    ```cli
    docker run -it --rm msolve-cantilever-image
    ```

    This **creates** and **starts** a docker container based on the msolve-cantilever-image created earlier.

    `-it` makes sure to attach our terminal to the container, so we can see the output.

    `--rm` makes sure to delete the container after the execution has finished.

  * If you want to create a container and be able to launch it on demand, you can use

    ```cli
    docker create --name msolve-cantilever-container msolve-cantilever-image
    ```

    This will just **create** a docker container based on the image created earlier. To verify that the container was created you can run

    ```cli
    docker ps -a
    ```

    You can then **start** the container by running

    ```cli
    docker start -a msolve-cantilever-container
    ```

    `-a` makes sure to attach our terminal to the container, so we can see the output.

    You can **delete** the container by running

    ```cli
    docker rm msolve-cantilever-container
    ```

* The docker image can be deleted by running
  
  ```cli
  docker rmi msolve-cantilever-image
  ```
