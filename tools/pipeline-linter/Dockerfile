# Copyright 2021 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# <http://www.apache.org/licenses/LICENSE-2.0>
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

FROM golang:alpine3.14

RUN apk add --no-cache git nodejs npm
RUN go install github.com/google/addlicense@v1.0.0
RUN export GO111MODULE=on && go install github.com/googlecodelabs/tools/claat@v2.2.0

# Install our dependencies
COPY *.sh /usr/bin/

# install apgieelint
RUN npm install --global apigeelint@latest

# Run script
WORKDIR /home
CMD ["check-licenses.sh"]